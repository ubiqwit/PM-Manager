# Ontario obligations for a Manager who collects and pays out funds

Research for [#2](https://github.com/ubiqwit/PM-Manager/issues/2) (map: [#1](https://github.com/ubiqwit/PM-Manager/issues/1)). Researched 2026-10-27. Terms as in `GLOSSARY.md`.

**This is not legal or tax advice.** It records what the primary sources say so the MVP can be shaped around them. Every "likely" below is a question to put to a lawyer or accountant.

## Setting

One Manager in Ontario administers about 15 fractionally owned, interest-only Mortgages. Borrowers pay Borrower Payments into the Manager's bank account. The Manager pays each Lender their Payout by cheque or e-transfer. Lenders are corporations, individuals, and one self-directed registered plan trustee. The Manager's own company is also a Lender. The Manager is registered for HST and remits it.

## 1. Licensing: what the Manager does is "administering mortgages"

- The Act defines administering mortgages as "Receiving payments from a borrower under a mortgage on behalf of another person or entity, and remitting the payments to or on behalf of that person or entity." ([MBLAA 2006, s. 5(1) para 1](https://www.ontario.ca/laws/statute/06m29#BK7))
- "No person or entity shall carry on the business of administering mortgages in Ontario unless he, she or it has a mortgage administrator's licence or is exempted from the requirement to have such a licence." ([MBLAA s. 5(2)](https://www.ontario.ca/laws/statute/06m29#BK7))
- The exemptions in the Act cover financial institutions (s. 6(2)), lawyers in prescribed circumstances (s. 6(6)), and prescribed others (s. 6(9)). ([MBLAA s. 6](https://www.ontario.ca/laws/statute/06m29))
- The prescribed exemptions from the administrator licence in [O. Reg. 407/07](https://www.ontario.ca/laws/regulation/070407) are narrow:
  - a lawyer administering in a professional capacity for a client (s. 5);
  - a trustee in bankruptcy, or someone acting under a court order (ss. 6 and 7);
  - acting for the Crown (s. 16);
  - acting for a financial institution or a listed finance company (s. 17);
  - a registered collection agency enforcing payment (s. 18);
  - administering only mortgages backing mortgage-backed securities (s. 19).
- **None of these is a small-book, related-party or "I'm also a Lender" exemption.** Collecting Borrower Payments for co-Lenders and remitting Payouts is the defined activity. The only open point is whether the Manager is "carrying on the business" of it. Charging fees for it on a continuing book of ~15 Mortgages points strongly toward yes. **Confirm licence status with FSRA or a lawyer.** If the Manager is not licensed, that is the most important finding here. The Act also bars an unlicensed person from suing to be paid for administering ([MBLAA s. 12(1)](https://www.ontario.ca/laws/statute/06m29)).
- Neighbouring activities that need a **brokerage** licence, not an administrator licence:
  - **Dealing in mortgages:** soliciting Lenders, or negotiating or arranging Mortgages for others ([MBLAA s. 2(1)](https://www.ontario.ca/laws/statute/06m29)).
  - **Trading in mortgages:** e.g. placing Shares with Lenders ([s. 3(1)](https://www.ontario.ca/laws/statute/06m29)).
  - **Carrying on business as a mortgage lender** ([s. 4](https://www.ontario.ca/laws/statute/06m29)). There is an exemption for lending solely through a brokerage ([O. Reg. 407/07 s. 15](https://www.ontario.ca/laws/regulation/070407)).
- A Mortgage with two or more Lenders is a "syndicated mortgage" under the brokerage rules ([O. Reg. 188/08 s. 1](https://www.ontario.ca/laws/regulation/080188)). Arranging new ones carries extra brokerage disclosure duties. Whether the Manager or the Manager's company does any of this is outside this ticket, but it is worth asking the same lawyer.

## 2. If licensed: standards of practice that touch record-keeping

These come from [O. Reg. 189/08, Mortgage Administrators: Standards of Practice](https://www.ontario.ca/laws/regulation/080189), current consolidation from 2022-03-01. Each Lender in a syndicated Mortgage is owed these duties individually (s. 2).

**Administration agreement (s. 18).** There must be a written agreement with each Lender. It must set out:
- the name the mortgage is registered in;
- any trust details;
- when a Lender may dispose of their interest;
- how every Borrower Payment is disposed of, "including penalties and bonuses";
- default and enforcement rights and costs;
- the administration fees and how they are calculated and paid.

The agreement is deemed to include duties to promptly notify each Lender of a subsequent encumbrance, any significant change, and any Borrower default.

**Disclosures with written acknowledgement:**
- the Manager's relationship to the Borrower (s. 19);
- conflicts of interest (s. 20), which is relevant because the Manager's company is a Lender;
- fees received from, or paid to, others (ss. 15–16).

These disclosures are due at least two business days before the agreement is signed (s. 22).

**Identity.** Take reasonable steps to verify each Lender's identity before agreeing to administer (s. 9).

**Payouts (s. 23).**
- Pay Lenders only out of funds the Borrower actually paid.
- Hold a Borrower's uncertified cheque until it clears.
- Redemption proceeds must be paid out promptly (s. 24).

**Records (s. 29).** Keep complete and accurate financial records, copies of all documents given to or received from Lenders, and every administration agreement. The financial records must separate deemed trust funds from other assets.

**Falsification.** Take adequate precautions against falsification of records (s. 30).

**Retention (s. 31).**
- Keep agreement records for at least 6 years after the agreement expires.
- Keep other required records for 6 years.
- Electronic records are fine if they can be produced promptly in understandable electronic and paper form, and the ability to retrieve them must last the whole period.

**Monthly principal reconciliation (s. 32).** Each month, reconcile the total principal owed by Borrowers against the total principal held for Lenders, and explain any difference.

**Deemed trust and trust account (ss. 33–39):**
- Money received from a Borrower for a Lender is deemed to be held in trust. The Manager's own fees and expense reimbursements are not (s. 33).
- Keep one designated trust account at a bank, credit union, loan or trust corporation, or retail association (s. 34).
- Deposit trust funds within 2 business days and keep them separate (s. 35). Interest earned on trust funds goes to the beneficial owner unless that owner agrees otherwise in writing.
- Keep a written record of every deposit (amount, date, payer, purpose, the Mortgage it relates to) and every disbursement (amount, date, payee, purpose, the Mortgage it relates to). Trust interest must be traceable to the deposit it relates to (s. 36).
- Prepare a **monthly trust reconciliation** within 30 days of the bank statement. It shows the differences from the bank's records and the balance owing to each person, and an officer signs and dates it to certify it (s. 37).
- Report any shortfall to FSRA immediately (s. 38).
- Prepare an **annual reconciliation** summarising the monthly ones, within 90 days of fiscal year-end (s. 39).

**Licensing conditions (outside the app):**
- errors and omissions insurance of at least $500,000 per occurrence and $1M per year (s. 27);
- a $25,000 financial guarantee (s. 28);
- a complaints process with a written record of complaints and responses (s. 26);
- policies and procedures (s. 25).

**Filings (outside the app, but fed by it):**
- An annual information return, due March 31 for the prior calendar year ([O. Reg. 193/08](https://www.ontario.ca/laws/regulation/080193); FSRA [Annual Information Returns](https://www.fsrao.ca/industry/mortgage-brokering/annual-information-returns-air) and [MA AIR Filing Guide](https://www.fsrao.ca/media/29881/download)).
- Audited financial statements, plus auditor reports on the books and on the trust account and assets under administration, within 90 days of fiscal year-end ([O. Reg. 193/08 s. 3](https://www.ontario.ca/laws/regulation/080193)).

FSRA pages returned 403 to automated fetching. The AIR and audit points come from e-Laws search excerpts and FSRA page titles, so verify them on fsrao.ca.

## 3. FINTRAC (federal anti-money-laundering)

- Since **2024-10-11**, mortgage administrators, brokers and lenders are FINTRAC reporting entities. FINTRAC defines a mortgage administrator as "a person or entity, other than a financial entity, that is engaged in the business of servicing mortgage agreements on real property ... on behalf of a lender" ([FINTRAC: Mortgage sector](https://fintrac-canafe.canada.ca/re-ed/mortgage-hypotheque-eng)).
- Obligations:
  - a compliance program (compliance officer, policies, risk assessment, training, two-year review);
  - know-your-client identity verification, beneficial ownership and politically-exposed-person determinations;
  - record keeping;
  - suspicious transaction, large cash, and listed/sanctioned property reports.
- This seems to apply whether or not the provincial licence question resolves either way, because FINTRAC's definition turns on the activity. Confirm it.

## 4. Income tax information slips

**T5, the rule.** Income Tax Regulations s. 201(1)(b) requires a T5 for interest "in respect of (A) money on loan to an association, corporation, institution, organization, partnership or trust" (among others). It does not cover a loan to an individual. ([ITR s. 201](https://laws-lois.justice.gc.ca/eng/regulations/C.R.C.,_c._945/section-201.html))

**T5, the agent rule.** "Every person who receives as nominee or agent for a person resident in Canada a payment to which subsection (1) applies shall make an information return." (ITR s. 201(2)) So when a Borrower is a corporation, partnership or trust, its interest is reportable. Because the Manager receives that interest as agent for the Lenders, the Manager may be the one who must issue T5s.

**CRA's T5 guide** ([T4015](https://www.canada.ca/en/revenue-agency/services/forms-publications/publications/t4015/t5-guide-return-investment-income.html)):
- Excluded from reporting: "interest one individual pays to another, such as interest paid on a private mortgage."
- Excluded: amounts paid or credited to non-residents. Those go on NR4, which is not researched here.
- Excluded: totals under $50 per recipient for the year.
- Due by the last day of February.
- Electronic filing is required for more than 5 slips.
- Slips need the recipient's SIN or BN. Failing to make a reasonable effort to get it can bring a $100 penalty.
- For a registered plan, the slip names the registered holder (the trustee), not the individual.
- You must keep the information the slips were prepared from in an accessible and readable format.

**What this means here.** Whether any T5 is due turns on **Borrower type**:
- individual Borrower: likely no T5 from anyone;
- corporate, partnership or trust Borrower: T5 for each resident Lender's share of interest, likely filed by the Manager as agent.

The Borrower record therefore needs a party-type field, and the Lender record needs a tax ID and residency. Confirm with an accountant who files, and whether the Lender's Fee counts as interest for slip purposes.

**T5013.** Only partnerships file it. Co-owners of a Mortgage are usually co-owners, not a partnership, so T5013 likely does not apply. Whether a particular syndication arrangement is a partnership is a legal question. Not researched further.

**The Manager's own books.** Keep records for 6 years from the end of the last tax year they relate to, in electronically readable form if kept electronically ([ITA s. 230(4)–(4.1)](https://laws-lois.justice.gc.ca/eng/acts/I-3.3/section-230.html)). GST/HST records have a parallel 6-year rule (ETA s. 286, not fetched).

## 5. HST on the Manager's fees

**Normally taxable.** Lending is an exempt "financial service" ([ETA s. 123(1) "financial service"](https://laws-lois.justice.gc.ca/eng/acts/E-15/section-123.html)). However, para (t) excludes "a prescribed service". The [Financial Services (GST/HST) Regulations s. 4(2)](https://laws-lois.justice.gc.ca/eng/regulations/SOR-91-26/FullText.html) prescribe "any administrative service, including an administrative service in relation to the payment or receipt of dividends, interest, principal ... other than solely the making of the payment or the taking of the receipt." So a third party's mortgage administration fee is **taxable**, which matches the Manager already charging and remitting HST.

**Possible exception.** Under s. 4(3), the service is *not* prescribed, and so is exempt, when it is supplied by:
- (a) a "person at risk" on the instrument, i.e. a Lender;
- (b) a member of the same closely related group as a person at risk;
- (c) the agent or broker who arranged the instrument.

If the Manager's administering entity is the same company that is a Lender, or closely related to it, or arranged the Mortgage, part or all of the fee could be exempt. **Have an accountant confirm which entity supplies the service and whether 4(3) applies.**

**Lender's Fee.** The Lender's Fee charged to the Borrower goes to the Lenders by Share. It is consideration connected with the loan, likely exempt and not the Manager's supply. Confirm this.

**For the app:** record the Manager's fee and the HST on it separately from Payouts, per Lender and per period, so the Manager can do HST returns outside the app.

## Conclusion: what the MVP must record or produce

**Record:**
1. Every Borrower Payment: date, amount, Borrower, Mortgage, and split into interest, principal and Lender's Fee. Flag uncertified cheques and their clearance date, because Payouts must wait for them (189/08 ss. 23 and 36).
2. Every Payout: date, amount, Lender, Mortgage, the source Borrower Payment, and method (cheque or e-transfer). The rule is never pay out more than was received for that Mortgage (s. 23).
3. Manager fees and the HST on them, kept separate from trust money (ss. 29(2) and 33(3)).
4. Trust account interest, if any, and who it belongs to (ss. 35(3) and 36).
5. Party data:
   - Lender type (individual, corporation, registered-plan trustee), residency, and SIN/BN for slips;
   - Borrower type (individual or not), which drives T5s;
   - date identity was verified (s. 9; FINTRAC).
6. Per-Lender administration agreement, disclosure and acknowledgement dates, plus a document reference (ss. 18–22). Store the reference, not the document.
7. Defaults, NSFs and subsequent encumbrances, with the date each Lender was notified (s. 18(3)).
8. Immutable history: no silent edits. Corrections are new entries, with an audit trail (s. 30).
9. Records kept and exportable for at least 6 years after the last agreement ends (s. 31; ITA s. 230).

**Produce:**
1. A monthly principal reconciliation: Borrower principal outstanding vs principal held for Lenders, with the difference explained (s. 32).
2. A monthly trust reconciliation working paper: the app's ledger balance per person against the bank statement balance the Manager enters (s. 37). Also an annual summary of the monthly reconciliations (s. 39).
3. Per-Lender periodic and year-end statements: interest, principal returned, Lender's Fee and Payouts per Mortgage. These feed T5s where needed, the Lenders' own tax filings, and the plan trustee's reporting.
4. A year-end T5 worksheet: per resident Lender, interest from non-individual Borrowers, with the $50 threshold applied. It supports filing outside the app.
5. A fee and HST summary per period for the HST return.
6. Export (CSV/PDF) for the auditor, FSRA examinations and FINTRAC requests.

**Outside the app (the Manager's own business):**
- the FSRA licence decision and licensing conditions (insurance, financial guarantee, policies, complaints process);
- the AIR and the audited financial statements;
- the FINTRAC compliance program and reports;
- the bank trust account itself;
- filing T5s (or NR4s) with CRA;
- HST returns;
- the legal documents (agreements, disclosures);
- the Manager's own corporate tax.

## Key uncertainties to confirm with a professional

1. **Licence:** is the Manager carrying on the business of administering mortgages and therefore required to hold an FSRA mortgage administrator licence? No exemption in O. Reg. 407/07 appears to fit. Also check whether any brokerage activity (soliciting Lenders, arranging Mortgages) is happening. *(lawyer / FSRA)*
2. **Trust account:** is the receiving bank account a designated trust account separate from the Manager's own money? If not, and the Manager is licensed, that is non-compliant (189/08 ss. 34–35). *(lawyer)*
3. **FINTRAC:** confirm reporting-entity status since 2024-10-11 and what compliance program is in place. *(lawyer / FINTRAC)*
4. **T5:** which Borrowers are non-individuals; whether the Manager files as agent under ITR 201(2); and how the Lender's Fee is characterised. *(accountant)*
5. **HST:** which entity supplies the administration service, and whether FS Regs s. 4(3) makes any of it exempt because the Manager's company is a Lender. *(accountant)*
6. **Non-resident Lenders:** if any exist, NR4 and Part XIII obligations. Not researched. *(accountant)*
7. **Registered-plan Lender:** what the trustee requires (annual valuation or statements) and qualified-investment rules. These are the trustee's and annuitant's concern, but they may set statement requirements. *(trustee)*

## Sources

- Mortgage Brokerages, Lenders and Administrators Act, 2006, S.O. 2006, c. 29: <https://www.ontario.ca/laws/statute/06m29>
- O. Reg. 407/07, Exemptions from the Requirements to be Licensed: <https://www.ontario.ca/laws/regulation/070407>
- O. Reg. 189/08, Mortgage Administrators: Standards of Practice: <https://www.ontario.ca/laws/regulation/080189>
- O. Reg. 188/08, Mortgage Brokerages: Standards of Practice: <https://www.ontario.ca/laws/regulation/080188>
- O. Reg. 193/08, Reporting Requirements for Licensees: <https://www.ontario.ca/laws/regulation/080193>
- FSRA, Annual Information Returns: <https://www.fsrao.ca/industry/mortgage-brokering/annual-information-returns-air>
- FSRA, Mortgage Administrator AIR Filing Guide: <https://www.fsrao.ca/media/29881/download>
- FINTRAC, Mortgage sector: <https://fintrac-canafe.canada.ca/re-ed/mortgage-hypotheque-eng>
- Income Tax Regulations, s. 201: <https://laws-lois.justice.gc.ca/eng/regulations/C.R.C.,_c._945/section-201.html>
- CRA, T4015 T5 Guide: <https://www.canada.ca/en/revenue-agency/services/forms-publications/publications/t4015/t5-guide-return-investment-income.html>
- Income Tax Act, s. 230: <https://laws-lois.justice.gc.ca/eng/acts/I-3.3/section-230.html>
- Excise Tax Act, s. 123(1) "financial service": <https://laws-lois.justice.gc.ca/eng/acts/E-15/section-123.html>
- Financial Services and Financial Institutions (GST/HST) Regulations, SOR/91-26, s. 4: <https://laws-lois.justice.gc.ca/eng/regulations/SOR-91-26/FullText.html>

e-Laws text was read from the official Word downloads (`ontario.ca/laws/docs/<id>_e.doc`), because the HTML pages are script-rendered.
