# Low-cost stack and hosting options for a single-user financial app

Research for issue #3 (child of map #1, "PM Manager MVP").
All pricing was read from first-party pages on **2026-10-27**. Prices are in USD unless marked otherwise and exclude tax. Re-check them before committing to a platform, because vendors change free tiers often.

## The question

One Manager administers about 15 Mortgages: the register of Mortgages, Terms, Lenders and Shares, recording Borrower Payments, calculating Payouts, maturity tracking and LTV. That comes to a few hundred rows a year. The data is sensitive financial information. The app records money and never moves it. Multi-tenancy is out of scope, but it may be marketed later.

**What the workload means.** The dataset will be kilobytes to low megabytes for years. Every option below fits inside a free tier or the smallest paid tier, so cost hardly separates them. The real differences are auth, backup/restore, where the data lives, maintenance, and lock-in.

## Options compared

| | A. Cloudflare Workers + D1 + Access | B. Small container + SQLite + Litestream (e.g. Fly.io Toronto) | C. Desktop app (Tauri) + encrypted SQLite | D. Managed Postgres BaaS (Supabase / Neon) | E. Local-first with cloud sync (Turso Sync) |
|---|---|---|---|---|---|
| **Monthly cost** | $0 on Free; $5 minimum on Workers Paid [1][2] | about $2–4 (machine $2.19 + volume $0.15/GB) [5]; B2 backup free under 10 GB [7] | $0 (optional B2 backup, free under 10 GB) | Supabase $0 Free (pauses) or $25 Pro [8]; Neon $0 Free or usage-based [9] | Turso $0 Free / $4.99 Developer [10] |
| **Auth for one user** | Cloudflare Access in front of the app: identity provider or email OTP, deny-by-default policies; Free plan $0 for up to 50 users [3][4]. No app-side auth code needed for the MVP. | Must build it (a single password + TOTP, or OAuth with an allow-listed email), or put Cloudflare Access / a tunnel in front. | OS login plus a database passphrase. No network attack surface. | Built-in auth (Supabase: 50k MAU on Free) [8] | Local passphrase; sync token held by the app |
| **Backup / restore** | D1 Time Travel point-in-time restore: 7 days on Free, 30 on Paid [12]. Longer retention means exporting to R2 yourself [12]. | Litestream streams SQLite changes continuously to S3/B2/SFTP/etc. and restores to the last replicated transaction [6][13]. Fly also takes daily volume snapshots with 5-day retention by default [5]. | Up to you: periodic encrypted file copies (OneDrive, or B2 via Litestream). Losing the device without a backup loses everything. | Supabase Free: **no backups**; Pro: daily, 7 days; PITR is a $100/mo add-on [8]. Neon Free: 6-hour restore window; Launch: up to 7 days [9] | Remote copy is the source of truth; PITR 1 day (Free) / 10 days (Developer) [10] |
| **Data at rest** | D1 encrypts objects with AES-256 (GCM), TLS in transit [11] | Disk encryption is the provider's; add app-level or SQLCipher encryption if wanted. Backups in B2 are under your own keys/bucket. | SQLCipher: 256-bit AES full-database encryption; Community edition is open source, commercial from $999/yr [14] | Provider-managed encryption | Local file can be encrypted with an `encryptionKey` you manage [15] |
| **Data residency** | D1 jurisdictions are only `eu`, `fedramp`, `us`; location hints include `enam`/`wnam` with no Canada option, and hints are not guarantees [16] | Fly has a Toronto region (`yyz`) [17] | On the Manager's machine (Ontario) | Supabase has `ca-central-1` [18] | Depends on Turso region |
| **Maintenance** | Lowest: no servers, no OS patching. Wrangler deploys. | Low to medium: you own the container image, dependency updates and Litestream configuration. Fly has no free tier for new orgs [5]. | Medium: build/sign installers, run an updater (Tauri updater requires its own signing keypair; losing the key means you cannot ship updates) [19]; plus OS code-signing. | Low, but the free tiers are hostile to a rarely used app (Supabase pauses after 1 week idle [8]; Neon suspends compute after 5 min, which is fine) | Medium to high: sync semantics (last-push-wins by row), WAL checkpointing; offline sync launched as a beta [20][21] |
| **Constrains later multi-tenancy?** | Moderately. Code is tied to the Workers runtime and D1 bindings, but D1 makes database-per-tenant cheap, and Access scales to 50 free seats. | Least. A plain web app plus SQLite can move to Postgres or database-per-tenant on any host. | Most. A desktop app has to be re-platformed into a hosted service to sell as SaaS. | Least on data (Postgres + row-level security is the standard multi-tenant shape), but costs $25+/mo from day one to be safe | High complexity. Sync plus multi-tenant is a hard combination. |

## Notes on the options

**A. Cloudflare Workers + D1 + Access.** This is the cheapest option with backups built in. The Workers Free plan allows 100,000 requests/day [2] and D1 Free allows 5M rows read/day and 5 GB [1], which is orders of magnitude above this workload. Cloudflare Access (Zero Trust Free, $0, 50 users [3]) removes the need to write login code: only the Manager's identity gets through, deny by default [4]. Avoid an "Include Everyone" or bare One-time-PIN policy; the docs warn that it lets anyone in [4]. Moving to Workers Paid ($5/mo) mainly buys 30-day Time Travel instead of 7 days [12]. The gap is Canada: there is no Canadian jurisdiction [16].

**B. Container + SQLite + Litestream.** This is the most portable option. Any small host works. Fly.io is the cheap example with a Toronto region: smallest machine $2.19/mo, volume $0.15/GB/mo, snapshots free under 10 GB, no platform fee, but no free tier for new organisations [5][17]. Litestream backs up continuously for "pennies" to Backblaze B2, where the first 10 GB is free [6][7][13]. A €5.99/mo Hetzner VPS is another option, but Hetzner listed its cheapest shared plans as "currently not available" and has no Canadian location [22], and a VPS adds OS patching. Auth is the main thing you have to build. Putting Cloudflare Access in front closes that gap.

**C. Desktop app (Tauri + SQLCipher).** This is the most private option: no server and nothing exposed to the internet. Tauri targets Windows/macOS/Linux using the system webview (from about 600 KB) [23]. SQLCipher gives full-database AES-256 encryption [14]. The costs are installer signing, an update channel [19], single-device use, and backup discipline. It also does the least for a later SaaS version.

**D. Managed Postgres BaaS.** **Not recommended** for the MVP. Supabase Free pauses after a week of inactivity and has no backups, so the first safe tier is $25/mo [8]. Neon Free keeps only 6 hours of restore history [9]. These services are a natural destination *if* multi-tenancy is ever built, not a starting point.

**E. Local-first with sync.** **Not recommended** for the MVP. The Turso Sync / offline-writes model works (local writes, explicit `push()`/`pull()`, last-push-wins by row) [15][20], but it launched as a beta that was not recommended for production [21], and one Manager on one or two devices does not need offline writes. The problem it solves (offline, multi-device) is not in the MVP.

## Short list (no single winner)

1. **Cloudflare Workers + D1 + Cloudflare Access**: $0–5/mo, no auth code, built-in 7/30-day point-in-time restore, no servers to maintain. Trade-offs: Workers-runtime lock-in, and no Canadian data residency.
2. **Portable web app + SQLite + Litestream to B2 on a small host (e.g. Fly.io `yyz` Toronto)**: about $2–4/mo, Canadian region, easiest path to a later multi-tenant version. Trade-offs: you build or bolt on auth (Cloudflare Access works here too), and you own the container upkeep.
3. **Tauri desktop app + SQLCipher**: $0/mo, data never leaves the Manager's machine. Trade-offs: installer signing and updates, single device, backups are your responsibility, and the hardest route to SaaS.

**Design hedge that applies to all three:** use SQLite with a thin data-access seam and store money as integer cents. Then A and B are largely interchangeable, and a later move to Postgres stays mechanical.

## Open questions this raises

- **Data residency.** Does anything (Lender agreements, the Manager's own policy, Ontario obligations research) require the data to stay in Canada? If so, option A drops off the list. This should feed into the Ontario obligations ticket.
- **Backup retention policy.** How far back must a restore reach (7 days, 30 days, years)? Year-end reporting may need annual snapshots kept outside any provider's PITR window. This belongs to the map's "Backups, security, and data retention" fog.
- **One device or several?** If the Manager needs phone access, option C weakens.

## Sources (all read 2026-10-27)

1. Cloudflare D1 pricing: https://developers.cloudflare.com/d1/platform/pricing/
2. Cloudflare Workers pricing: https://developers.cloudflare.com/workers/platform/pricing/
3. Cloudflare SASE / Zero Trust plans: https://www.cloudflare.com/plans/sase-zero-trust.md
4. Cloudflare Access policies: https://developers.cloudflare.com/cloudflare-one/access-controls/policies/
5. Fly.io pricing: https://docs.fly.io/about/pricing
6. Litestream: https://litestream.io/
7. Backblaze B2 pricing: https://www.backblaze.com/cloud-storage/pricing
8. Supabase pricing: https://supabase.com/pricing
9. Neon pricing: https://neon.com/pricing
10. Turso pricing: https://turso.tech/pricing
11. D1 data security: https://developers.cloudflare.com/d1/reference/data-security/
12. D1 Time Travel: https://developers.cloudflare.com/d1/reference/time-travel/
13. Litestream guides (replica backends): https://litestream.io/guides/
14. SQLCipher: https://www.zetetic.net/sqlcipher/
15. Turso embedded replicas: https://docs.turso.tech/features/embedded-replicas/introduction
16. D1 data location: https://developers.cloudflare.com/d1/configuration/data-location/
17. Fly.io regions: https://docs.fly.io/reference/regions/
18. Supabase regions: https://supabase.com/docs/guides/platform/regions
19. Tauri updater plugin: https://v2.tauri.app/plugin/updater/
20. Turso Sync usage: https://docs.turso.tech/sync/usage
21. Turso offline sync public beta: https://turso.tech/blog/turso-offline-sync-public-beta
22. Hetzner Cloud: https://www.hetzner.com/cloud/
23. Tauri: https://v2.tauri.app/
