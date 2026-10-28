# PM Manager

A tool for a private mortgage manager to administer a small book of privately funded, fractionally owned mortgages.

## Parties

**Manager**:
The person who administers a book of private mortgages on behalf of the Lenders who fund them. A role, never a Lender in itself.
_Avoid_: Admin, broker, servicer

**Lender**:
A corporation, individual or organization holding a Share in a mortgage. The Manager's own company may be a Lender, and is treated like any other.
_Avoid_: Investor, shareholder, participant

**Borrower**:
The party a mortgage is lent to, who pays interest and repays principal.

**Guarantor**:
A person who is not the Borrower but promises to repay a Mortgage if the Borrower doesn't.
_Avoid_: Co-signer

## Mortgages

**Mortgage**:
A simple-interest loan to a Borrower, secured on property and funded by one or more Lenders holding Shares in it. Usually interest-only; some repay principal with interest in blended payments.
_Avoid_: Loan, deal, file

**Term**:
One period of a Mortgage, with its own rate, Payment Day, start and maturity dates; a renewal, an extension, or any rate change begins a new Term on the same Mortgage.
_Avoid_: Renewal period, extension

**Payment Day**:
The day of the month on which a Term's interest, or blended payment, falls due for the month just ended.
_Avoid_: Due date, anniversary

**Stub**:
Interest for a part of a month, counted by actual days over 365.
_Avoid_: Broken period, per diem period

**Overholding**:
A Mortgage past its last Term's maturity, neither renewed nor repaid, still bearing interest at that Term's rate.
_Avoid_: Holdover, expired mortgage

**Principal Event**:
A dated change to a Lender's principal in a Mortgage: an advance, a capitalised Lender's Fee, a principal repayment, a Redemption, or a Share Sale.
_Avoid_: Adjustment, transaction

**Share**:
The principal a single Lender has in a Mortgage; its percentage is that principal over the Mortgage's total principal.
_Avoid_: Stake, portion, participation

**Share Sale**:
One Lender selling all or part of its Share to another Lender; the Mortgage's total principal is unchanged.
_Avoid_: Assignment, transfer

**Redemption**:
Repayment of one Lender's Share while the Mortgage continues for the remaining Lenders.
_Avoid_: Transfer, buyout

**Lender's Fee**:
A fee charged to the Borrower on a Term, separate from interest, split among Lenders by Share; it is paid by the Borrower, deducted from the advance, or capitalised into principal. A rate quoted as "including the fee" is all interest, not a Lender's Fee.
_Avoid_: Origination fee, admin fee, renewal fee

**Collateral**:
Additional property pledged against a Mortgage beyond the primary property, carrying a value set by the Manager.
_Avoid_: Security, guarantee

**Prior Charge**:
A mortgage registered ahead of ours on the same property, which counts against the property's value when judging LTV.
_Avoid_: First mortgage, senior debt

**Valuation**:
A dated value of a property, set by the Manager, with its basis: an appraisal, a broker's opinion, an assessment, or the Manager's own estimate. A property keeps every Valuation; the latest one counts.
_Avoid_: Appraisal (one basis among several), appraised value

**LTV**:
Loan-to-value: a Mortgage's outstanding principal plus the Prior Charges ahead of it, over the latest Valuations of the properties securing it. Stated both on the primary property alone and with its Collateral included.
_Avoid_: Leverage, coverage

## Money

**Borrower Payment**:
Money received from a Borrower on a Mortgage: interest, principal, or a Lender's Fee.

**Payout**:
Money the Manager pays a Lender as their Share of a Borrower Payment.
_Avoid_: Distribution, cash out
