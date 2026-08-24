# Flagship Growth Desk – First Weekend Setup Checklist
**Target: Solo operator | Manual execution | Adaptive thematic concentration**

This is the practical companion to `Grok Bot - Flagship Growth Desk.txt` (v1.3 Lean + Graph).  
Follow the steps in order. Do not skip the folder scaffold.

---

## 1. Create the Shared Workspace (Do this first)

```
/workspace/
├── watchlist.csv
├── model_portfolio.json
├── briefs/
├── weekly/
├── cache/
│   ├── filings/
│   ├── transcripts/
│   ├── prices/
│   └── graphs/
├── state/
├── calendar/
└── evolve/
    └── proposals/
```

Also create `/workspace/state/adaptive_rules.json` and `/workspace/state/graph_health.json` (can start as `{}`).

---

## 2. Seed the Two Core Files

Copy from this repo into `/workspace/`:

- `watchlist.csv` → research universe
- `model_portfolio.json` → live 15–20 name concentrated model book

Edit them freely. The desk is designed to evolve the theme.

---

## 3. Universe Design

| Layer              | Size          | Purpose                                      | Who owns it                |
|--------------------|---------------|----------------------------------------------|----------------------------|
| Research Universe  | ~80–120 names | Overnight coverage                           | You + Theme & Catalyst     |
| Model Portfolio    | 15–20 names   | Concentrated high-conviction book            | Portfolio Construction Bot |

The bots research the curated watchlist deeply. They do not attempt to cover the entire S&P 500 or Nasdaq every night.

---

## 4. Create the 9 Bots

Paste the system prompts from Section 10 of the main document (v1.3 Lean + Graph):

1. Research Analyst (filings + earnings + sentiment + insider)
2. Macro & Cycle Analyst
3. Theme & Catalyst Analyst
4. Valuation & Lynch Classifier
5. Graph & Spatiotemporal Engineer (Hermes modular layer)
6. Portfolio Construction Bot
7. Calendar Bot
8. Desk Lead / Coordinator
9. Evolve Controller

After creation, tell Desk Lead:  
“You are the primary checker. Learn the overnight routine and the weekly Flagship cycle from the architecture document.”

---

## 5. Connect Google Calendar

Authorize Calendar Bot to create events on your primary Google Calendar.

---

## 6. First Manual Cycle (Validation)

1. Trigger Research Analyst (or let the schedule run one night).
2. Confirm dated briefs under `/workspace/briefs/`.
3. Run Desk Lead once and inspect the coordinator brief.
4. Confirm HIGH / MEDIUM sections appear cleanly.

---

## 7. Go Live

- Let overnight run for 5–7 market nights.
- First Sunday/Monday: Flagship Weekly Report + rebalance suggestions.
- Review, decide, execute **manually**.

After 2–3 weeks, run the first Evolve cycle.

---

## 8. Recommended First Edits

- Trim or expand `watchlist.csv`.
- Adjust starting weights in `model_portfolio.json`.
- Add personal high-conviction names.
- Tell Macro & Cycle your preferred max cash / gold / BTC sleeve sizes.

---

## Quick Mental Model

- Overnight = combined research coverage (filings, earnings, sentiment, insider) + Graph update
- Weekly = decision + concentrated model portfolio update (with adaptive notes)
- Calendar = never miss a catalyst or review date
- Adaptive Layer = hybrid position sizing, regime awareness, concentration guardrails (Graph-informed), smart cash
- Graph = modular correlation / lag / regime / concentration layer (reversible, never critical path)
- Evolve = measured improvement of research rules and adaptive sizing (with your approval)
- You = final decision and all execution

Version 1.3 is the lean build with Graph restored (9 bots). Still robust. Start simple. Iterate with Evolve where it helps.

See `changes/CHANGES.md` for what was removed from the original 13-bot design.

---

## 9. Libraries & Dependencies (if NOT running on Grok Bot)

```bash
pip install -r requirements.txt
```

Core: pandas, numpy, yfinance, requests, beautifulsoup4, lxml  
Filings: sec-edgar-downloader (or pure requests)  
Graph: networkx, scipy  
Calendar: python-dateutil, pytz, google-api-python-client if needed

See `requirements.txt` for the full list.

---

**Files in this repo:**
- `Grok Bot - Flagship Growth Desk.txt` (v1.3 Lean + Graph — primary system)
- `SETUP.md` (this file)
- `changes/CHANGES.md` (what was cut and restored)
- `watchlist.csv`
- `model_portfolio.json`
- `requirements.txt`
- Original Hedge Fund Research Desk files = archived backup only
