# Lookthrough

An independent rating app for private-market funds that non-accredited (retail) investors can buy. Built as a fintech class project.

Big platforms (Robinhood, Destiny, Fundrise, ARK and others) now sell everyday investors exposure to private companies like OpenAI, Anthropic and Databricks. Lookthrough takes no money from those funds and rates each one on what a retail buyer actually gets:

- **Look-through exposure:** how much of each company $100 in the fund really buys
- **Price vs assets:** premium or discount to the fund's last reported NAV
- **True cost:** yearly expenses plus upfront sales loads
- **Getting money out:** daily trading vs. capped quarterly buybacks
- **Freshness and transparency:** how old the NAV is and how often holdings are disclosed

It also includes a readiness check that sets an allocation cap for alternatives, and a portfolio view that combines a user's funds into their underlying holdings.

## Funds covered

| Ticker | Fund | Structure |
|---|---|---|
| RVI | Robinhood Ventures Fund I | Exchange-traded closed-end fund |
| DXYZ | Destiny Tech100 | Exchange-traded closed-end fund |
| VCX | Fundrise Innovation Fund | Exchange-traded closed-end fund |
| ARKVX | ARK Venture Fund | Interval fund |
| PRIVX | The Private Shares Fund (Class A) | Interval fund |
| XOVR | ERShares Private-Public Crossover ETF | ETF |

Figures are from public filings and fund data dated mostly June to November 2026. See [`docs/data-sources.md`](docs/data-sources.md). **The data is a snapshot, not live, and must be re-checked before any presentation.**

## Running it

There is no build step. The whole app is one self-contained file, `index.html` (HTML, CSS and vanilla JavaScript).

- **Locally:** open `index.html` in a browser. An internet connection is needed only for the Google Fonts; without it the page falls back to system fonts.
- **Local server (optional):** `python3 -m http.server 8000`, then visit `http://localhost:8000`.
- **GitHub Pages:** Settings → Pages → deploy from the default branch, root folder. `index.html` is served as the home page.

Views are routed by URL hash: `#home`, `#companies`, `#portfolio`, `#ready`, `#method`, `#fund-<id>` (for example `#fund-rvi`) and `#company-<id>` (for example `#company-openai`).

## Project structure

```
lookthrough/
├── index.html              # The app: styles, data, scoring logic and views
├── README.md
├── .gitignore
└── docs/
    ├── concept.md          # Product concept, positioning, business model, stress test
    ├── methodology.md      # Scoring formula and weights
    ├── data-sources.md     # Every fund figure with its as-of date and source link
    └── transfer-inventory.md  # What was moved into this repo and what wasn't
```

## Where things live in `index.html`

- **Data:** the `COMPANIES`, `FUNDS` and `ALERTS` constants near the top of the `<script>` block. Update figures here.
- **Scoring:** `scores()` and `grade()` under `// ---------- Math ----------`.
- **Views:** `viewHome`, `viewFund`, `viewCompanies`, `viewCompany`, `viewPortfolio`, `viewReady`, `viewMethod`.
- **State:** user portfolio amounts and readiness answers live in memory only and reset on reload.

## Suggested next steps for the team

1. Re-verify every figure against primary sources (fund websites, SEC EDGAR filings) and update the dates.
2. Move `FUNDS` and `COMPANIES` into a `data/funds.json` file so data edits don't touch app code.
3. Split CSS and JavaScript into their own files if the app grows.
4. Build the pitch deck around the demo.

## Disclaimer

Class prototype. Not investment advice, not affiliated with any fund or sponsor listed, and not real-time data.
