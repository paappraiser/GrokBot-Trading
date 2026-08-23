# Flagship Growth Desk – First Weekend Setup Checklist
**Target: Solo operator | Manual execution | Adaptive thematic concentration**

This is the practical companion to `Grok Bot - Flagship Growth Desk.txt`.  
Follow the steps in order. Do not skip the folder scaffold.

---

## 1. Create the Shared Workspace (Do this first)

On the Grok Bot shared cloud computer, create exactly this structure:

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

You can create the empty folders with simple commands or by having any bot create them.  
Also create `/workspace/state/adaptive_rules.json` (can start as `{}`).

---

## 2. Seed the Two Core Files

Copy the starter files from this repo into `/workspace/`:

- `watchlist.csv` → research universe (broader list the bots actually read overnight)
- `model_portfolio.json` → the live 15–20 name concentrated model book

These starters are themed around AI / datacenter infrastructure / healthcare / crypto as of mid-2026.  
**Edit them freely.** The desk is designed to evolve the theme.

---

## 3. Universe Design (Important)

| Layer              | Size          | Purpose                                      | Who owns it                  |
|--------------------|---------------|----------------------------------------------|------------------------------|
| Research Universe  | ~80–120 names | Overnight coverage by research bots          | You + Thematic Detector      |
| Model Portfolio    | 15–20 names   | Concentrated high-conviction book            | Portfolio Construction Bot   |

The bots **do not** attempt to cover the entire S&P 500 or Nasdaq every night.  
That would produce noise and lower signal quality.  

They research the curated watchlist deeply.  
New names can still be discovered and proposed (insider clusters, extreme catalysts, thematic rotation evidence). You decide whether to add them.

---

## 4. Create the 13 Bots

Create each bot and paste the full system prompt from Section 11 of the main document (v1.1):

1. Filings Analyst  
2. Earnings Analyst  
3. Sentiment Analyst  
4. Insider Tracker  
5. Macro & Cycle Analyst  
6. Thematic Regime Detector  
7. Catalyst & Power Tracker  
8. Valuation & Lynch Classifier  
9. Graph & Spatiotemporal Engineer  
10. Calendar Bot  
11. Portfolio Construction Bot  
12. Desk Lead / Coordinator  
13. Evolve Controller  

After creation, give Desk Lead a short instruction:  
“You are the primary checker. Learn the overnight routine and the weekly Flagship cycle from the architecture document.”

---

## 5. Connect Google Calendar

Authorize the Calendar Bot (or the Desk) to create events on your primary Google Calendar.  
It will push earnings, catalysts, Form 4 windows, accumulation-zone reviews, and macro events.

---

## 6. First Manual Cycle (Validation)

1. Manually trigger Filings Analyst, Earnings Analyst, Insider Tracker, Sentiment Analyst (or let the schedule run one night).  
2. Confirm dated briefs appear under `/workspace/briefs/`.  
3. Manually run Desk Lead once and inspect the coordinator brief.  
4. Confirm it produces HIGH / MEDIUM sections cleanly.

If anything fails, fix the folder permissions or prompt scope before going live.

---

## 7. Go Live

- Let the overnight routine run for 5–7 market nights.  
- On the first Sunday/Monday, have Desk Lead + Portfolio Construction produce the first Flagship Weekly Report + rebalance suggestions (now including adaptive notes).  
- Review, decide, and execute any trades **manually**.  

After 2–3 weeks of real signals, run the first Evolve Controller cycle and begin the self-improvement loop.

---

## 8. Recommended First Edits (Optional but Smart)

- Trim or expand `watchlist.csv` to names you actually want coverage on.  
- Adjust starting weights in `model_portfolio.json` to match your risk tolerance.  
- Add any personal high-conviction names you already own or want researched.  
- Tell Macro & Cycle Analyst your preferred max cash / gold / BTC sleeve sizes.

---

## Quick Mental Model

- Overnight = research coverage of the watchlist  
- Weekly = decision + concentrated model portfolio update (with adaptive scale-in / scale-out notes)  
- Calendar = never miss a catalyst or review date  
- Adaptive Layer = hybrid position sizing, regime awareness, correlation governor, smart cash  
- Evolve = the desk improves both research quality and adaptive sizing rules over time  
- You = final decision and all execution  

You are not trying to build a high-frequency machine.  
You are building a high-conviction, cycle-aware, self-improving Flagship-style desk that works while you sleep and presents clear recommendations once a week.

Start simple. Iterate with Evolve. Compound.

---

## 9. Libraries & Dependencies (Important if NOT running on Grok Bot)

The original architecture assumed Grok Bot’s native computer-use and ephemeral code execution.  
If you are testing or running the desk **outside** Grok Bot (local Python, another agent platform, custom orchestration, etc.), install the packages listed in `requirements.txt`.

```bash
pip install -r requirements.txt
```

### Core recommended packages

| Category                  | Packages                                      | Purpose                                      |
|---------------------------|-----------------------------------------------|----------------------------------------------|
| Data & prices             | pandas, numpy, yfinance, requests             | Price history, dataframes, HTTP              |
| Filings / EDGAR           | sec-edgar-downloader, beautifulsoup4, lxml    | Download & parse 10-K/10-Q/8-K/Form 4        |
| Graph & Spatiotemporal    | networkx, scipy, scikit-learn                 | Correlation graphs, lag analysis, regimes    |
| Time & calendar           | python-dateutil, pytz, schedule               | Dates, timezones, local scheduling           |
| Google Calendar (local)   | google-api-python-client + auth libs          | Create/update events from Python             |
| Visualization (optional)  | matplotlib, plotly                            | Graph health or portfolio snapshots          |

Standard library modules (json, pathlib, datetime, csv, logging) are sufficient for state management and most I/O.

### Notes for non-GrokBot environments

- The system prompts remain the same. The bots still expect the `/workspace/` folder structure.
- Replace any “native X integration” or Grok-specific tools with equivalent API calls or data sources you have access to.
- For Calendar Bot: either keep using connected Google tools if available, or switch to the Google Calendar Python client listed above.
- Graph & Spatiotemporal Engineer can run pure pandas + networkx correlation matrices and simple lag features without heavy ML.
- Keep the maker-checker separation and the Evolve human-approval gate even if you re-implement the orchestration layer yourself.

See `requirements.txt` in this repo for the exact pin-friendly list.

---

**Files in this repo for setup:**
- `Grok Bot - Flagship Growth Desk.txt` (full architecture + all prompts, v1.1 with Adaptive Layer)
- `SETUP.md` (this file)
- `watchlist.csv` (starter research universe)
- `model_portfolio.json` (starter concentrated book)
- `requirements.txt` (Python libraries for non-GrokBot use)
