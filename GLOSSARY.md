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
One Lender selling all or part of its Share to another Lender, paid with the buyer's money; the Mortgage's total principal is unchanged.
_Avoid_: Assignment, transfer

**Redemption**:
Repayment of all or part of one Lender's Share out of the Borrower's money, while the Mortgage continues for the remaining Lenders. Any other repayment of principal is shared among all Lenders by Share.
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
Money received from a Borrower on a Mortgage, applied to interest, principal, a Lender's Fee or a Borrower Charge; whatever isn't applied is Unapplied.

**Borrower Charge**:
A dated amount the Borrower owes beyond interest, principal and the Lender's Fee, such as an NSF fee or a cost the Lenders paid to protect the Mortgage. It bears no interest.
_Avoid_: Penalty, add-on, disbursement

**Lender Cost**:
A cost paid to a third party to protect a Mortgage, borne by its Lenders by Share or by named Lenders, and funded by their contributions or deducted from what they are owed.
_Avoid_: Expense, deduction, disbursement

**Cleared**:
A Borrower Payment is cleared once its money is available in the bank account, on the day it is received unless the Manager sets a later day. Only Allocations from cleared Borrower Payments can be Paid Out.
_Avoid_: Settled, posted, available

**Unapplied**:
Money received from a Borrower that isn't yet applied to anything the Borrower owes, such as an overpayment or money left for future principal, held for that Borrower until it is applied to any of their Mortgages or refunded.
_Avoid_: Suspense, credit balance

**Arrears**:
What a Borrower owes and hasn't paid, worked out from interest and charges due less what has been applied, and aged by the oldest unpaid month.
_Avoid_: POS, delinquency, past due

**Waiver**:
Lenders forgiving interest or a Borrower Charge a Borrower owes, for a period or an amount, shared among them as it would have been paid.
_Avoid_: Write-off, forgiveness

**Reversal**:
An entry that cancels an earlier entry, with a date and a reason; records are never edited or deleted. An NSF is a Reversal of a Borrower Payment.
_Avoid_: Correction, void, adjustment

**Allocation**:
A Lender's entitlement to part of a Borrower Payment, by Share.
_Avoid_: Distribution, split

**Payout**:
Money the Manager actually pays a Lender, settling one or more Allocations; it may be later than, or less than, what the Lender is owed.
_Avoid_: Distribution, cash out

## Reporting

**Lender Statement**:
An account to one Lender, for a chosen period, of its Shares, Allocations, Waivers, Lender Costs and Payouts across every Mortgage it holds, with what it is still owed. Over a calendar year it is the year-end statement.
_Avoid_: Investor report, remittance advice

**Reconciliation**:
A dated comparison of the bank statement for a period with the Mortgage money recorded over it. What the statement shows beyond that money is left unreconciled as Non-Mortgage credits and debits. It also checks the bank holds at least the Mortgage money held for Borrowers and Lenders.
_Avoid_: Bank rec, trust rec, principal reconciliation

**Income Report**:
Every Lender's interest and Lender's Fee for a calendar year, per Mortgage, dated by Allocation, for an accountant to prepare tax slips from. It informs filing; it is not a slip.
_Avoid_: T5 worksheet, tax report
