# Scoring methodology

Implemented in `scores()` in `index.html`. Each sub-score runs 0–100.

| Part | Weight | Formula |
|---|---|---|
| Price vs assets | 30% | Premium `p = price / NAV − 1` (listed closed-end funds only; interval funds and ETFs use 0). If `p > 0`: `100 − 180p`. If `p ≤ 0`: `100 − 40·abs(p)` (discounts are penalized lightly because they can persist). |
| True cost | 25% | `annualCost = expense + load / 5` (sales load spread over 5 years). Score `100 − 25·(annualCost − 0.5)`. |
| Getting money out | 20% | ETF 100; exchange-traded closed-end fund 90; interval fund 40; interval fund with recent prorated buybacks 30. |
| NAV freshness | 15% | `100 − navAgeDays / 2`. |
| Transparency | 10% | Holdings disclosed daily 100, monthly 80, on a website without dates 70, quarterly 55. |

All sub-scores are clamped to 0–100.

**Total** = weighted sum. **Grades:** A ≥ 80, B ≥ 68, C ≥ 55, D ≥ 42, otherwise F.

## Derived figures

- **Assets per $100:** `100 × (1 − load/100) / (1 + p)`.
- **Exposure to a company per $100:** assets per $100 × the company's weight in the fund.
- **Still-private share:** sum of weights in companies marked `private`, plus "other private companies" where a fund reports them.

## Readiness rungs

| Rung | Condition | Cap (share of investable assets) |
|---|---|---|
| 0 | Under 3 months of expenses saved, or carrying high-interest debt | 0% |
| 1 | 3+ months saved, no high-interest debt | 5% |
| 2 | 6+ months saved | 10% |
| 3 | 6+ months saved and $25,000+ investable | 15% |

These weights and thresholds are design choices for the prototype, not industry standards. Expect to defend them.

## Known limitations

- The score measures fairness to the buyer, not purity of private exposure. XOVR scores highest but is mostly public stocks. Read the score together with the still-private share.
- Premiums for listed funds compare a current price with a NAV that may be months old.
