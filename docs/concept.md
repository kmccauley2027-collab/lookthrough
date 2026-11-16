# Lookthrough: product concept

## Problem

Retail investors can now buy private-market exposure without being accredited, through listed closed-end funds, interval funds and ETFs. Each sponsor markets its own fund. None of them tells the buyer:

- that the fund may trade far above (or below) the value of what it holds,
- how little of the headline company (SpaceX, OpenAI) each dollar actually buys,
- the full yearly cost, including loads and fees charged on cash,
- or that buybacks can be capped and prorated.

Lower-income investors are hurt most, because they have the least room for illiquid, expensive or overpriced positions.

## Positioning

An independent referee between retail investors and the platforms selling private-market funds: Morningstar crossed with Credit Karma, built only for this category. Independence is the product. Lookthrough takes no payments from fund sponsors.

## Core features

1. **Fund ratings:** an A–F grade and five sub-scores per fund (see `methodology.md`).
2. **Company view:** pick a company and see every fund holding it, ranked by exposure per $100.
3. **What $100 buys:** a stacked bar splitting $100 into underlying holdings, plus any premium or sales load with no assets behind it.
4. **Now-public flag:** highlights holdings that have since gone public (for example SpaceX in June 2026), which investors could buy directly with no fund fee.
5. **My Lookthrough:** combines a user's funds into underlying holdings, overlap, fees per year, illiquid share and minimum-investment checks.
6. **Readiness check:** emergency fund, high-interest debt and investable assets set a rung (0–3) and an allocation cap (0%, 5%, 10%, 15%).
7. **Alerts:** dated events such as premium swings, prorated buybacks and fee-on-cash issues.

## Business model options

1. **Freemium consumer app:** free scores; paid alerts, overlap and portfolio tools.
2. **Business data API (strongest):** license scores to RIAs, wealth management firms and financial media, which need independent support for suitability documentation.
3. **Affiliate fees from funds:** rejected. It conflicts with the independence that is the product.

## Regulatory line

- Impersonal analytics shown the same way to everyone can generally rely on the publisher's exclusion from the Investment Advisers Act.
- Personalized recommendations would require investment adviser registration and a fiduciary duty.
- Executing trades would require a broker-dealer or a broker-dealer partner.

So the product scores and alerts. It does not recommend or execute. The readiness check is framed as education.

## Stress test (expected objections)

| Objection | Response |
|---|---|
| The market is too small | Launch with private tech funds, then expand to all semi-liquid retail alternatives: interval funds, non-traded REITs, non-traded BDCs, private credit. |
| Morningstar already rates funds | Morningstar isn't built around premium to NAV, NAV staleness or look-through exposure for this category. Focus and speed are the edge. |
| The data is stale | Don't claim live data. Show the age of every figure. Honesty about lag is part of the brand. |
| Why would users come back? | Event alerts and a weekly digest of what moved in their holdings. |
| It's a wrapper on other people's funds | The premium meter and exposure data are what sponsors won't build, because they make their own products look worse. |

## Ideas considered and dropped

- **Rung:** an alternatives marketplace with a suitability gate. Dropped because platforms like Fundrise already cover the marketplace.
- **Prediction markets on private companies (Kalshi-style):** dropped. Polymarket launched this in May 2026, and it's betting, not investing.
- **No-loss prediction market (betting only the T-bill interest):** dropped. Still betting.
