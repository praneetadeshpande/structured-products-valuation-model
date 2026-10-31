# Structured Products Valuation Model

An Excel model of a loan pool and a two-tranche (Senior/Junior) structured product, built in four stages. Every number is a live formula, so changing an input updates the whole workbook.

**File:** `Model4_Sensitivity_Tables.xlsx`
**Start with:** the `Read Me` sheet in the workbook (plain-English glossary), then `Sensitivity`.

## What it does

| Stage | Sheets | What it covers |
|---|---|---|
| 1. Loan pool cash flows | `Inputs`, `Cash Flows` | Monthly cash flows for a pool of level-pay loans, after prepayments (CPR), defaults (CDR) and loss severity. Discounted to a price. |
| 2. Two-tranche waterfall | `Deal`, `Waterfall` | Senior is paid interest and principal first. Losses hit the Junior first. Each tranche is priced at its own discount rate. |
| 3. Yield and price solving | `Yield` | Price to yield using IRR and Goal Seek, yield to price, and weighted average life (WAL). |
| 4. Sensitivity analysis | `Sensitivity`, `Scenarios` | Price grids for the pool, Senior and Junior across default scenarios and discount-margin shifts. |

## Key takeaways (illustrative inputs)

- Higher defaults sharply reduce the Junior price, while the Senior price barely moves. Losses hit the Junior first, so it protects the Senior.
- Price and yield move in opposite directions. A tranche priced below 100 yields more than its coupon.
- Prepayments return principal early, which shortens the WAL.

## Built-in checks

- Tranche balances reconcile to the pool balance in every month.
- Balances reconcile: defaults + principal + prepayments + ending balance equal the starting balance.
- The yield solved by IRR re-prices exactly to the price paid.
- The sensitivity base case matches the `Inputs` and `Deal` sheets.

## Assumptions and simplifications

- All inputs are **illustrative example assumptions**, not market data.
- One coupon, term and severity for the whole pool. Level-pay loans.
- Recoveries arrive in the same month as the default (no lag).
- No servicing fees, triggers or reserve accounts. Unpaid interest is not carried forward. Excess interest is not used to cover losses.
- Yields are to the projected scenario, not guaranteed returns.

## Tools

Microsoft Excel (formulas, IRR, NPV, PMT, SUMPRODUCT, Goal Seek).# structured-products-valuation-model
Excel model of a loan pool and two-tranche structured product: cash flows, waterfall, yield solving and sensitivity analysis.
