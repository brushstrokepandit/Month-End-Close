# 2. Month-End Close Simulation (October 2026)

**File:** `Month_End_Close_Oct2026.xlsx` | **Data:** synthetic, INR | **Company:** fictional trading business

## Objective
Simulate the monthly accounting close end to end: post transactions, make month-end adjustments, produce a trial balance and financial statements, and run control checks before sign-off.

## Flow
`Chart_of_Accounts` -> `Journal` (single source of truth) -> `General_Ledger` and `Trial_Balance` -> `Income_Statement` and `Balance_Sheet` -> `Close_Checks`

## Volume
131 journal entries (1 opening, 125 regular, 5 adjusting) and 332 journal lines on 23 accounts.

## Adjusting entries
Accrued utilities and audit fee, accrued salaries for unpaid days, release of prepaid insurance, monthly depreciation (straight line).

## Trial balance worksheet
Unadjusted, adjustments and adjusted columns side by side, calculated with `SUMIFS` on account code and journal type (Opening / Regular / Adjusting).

## Close checks (all PASS)
Journal debits = credits, every journal balances, valid account codes, unadjusted and adjusted trial balances balance, ledger nets to nil, balance sheet balances.

## Assumptions
GST 18% shown net in one account; COGS at 62% of sales (booked weekly); depreciation 5 years straight line; no income tax provision.

## What I learned / how to explain it
Every statement figure traces back to journal lines through the trial balance, so an error can be located by drilling down: statement -> TB -> GL -> journal.
