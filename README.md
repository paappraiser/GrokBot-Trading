# GrokBot-Trading

**Primary system: Flagship Growth Desk (v1.3 Lean + Graph)**

This repo contains one active trading-research system and one archived backup.

---

## Use This One

**`Grok Bot - Flagship Growth Desk.txt`**

This is the system to run.  
It is a concentrated, adaptive research + recommendation desk designed to help beat the S&P 500 and QQQ over time.

- 15–20 high-conviction names
- Adaptive position sizing (scale-in / partial profit-taking)
- Weekly rebalance suggestions
- Macro / cycle awareness
- Theme can rotate when evidence changes
- **Graph & Spatiotemporal Engineer** (modular, Hermes-style — correlation, lag, regime, concentration)
- Measured self-improvement (with your approval)
- You still execute every trade manually

Version 1.3 is the lean build with Graph restored: **9 bots**. Research functions remain combined. Graph is full modular bot, reversible, never in the critical path.

Supporting files:
- `SETUP.md` — first-weekend checklist
- `changes/CHANGES.md` — what was removed from the 13-bot design and what the current system contains
- `watchlist.csv` — starter research universe
- `model_portfolio.json` — starter concentrated book
- `requirements.txt` — Python packages if running outside Grok Bot

---

## Archived / Backup Only — Do Not Use

**`Grok Bot - Hedge Fund Research Desk.txt`**  
**`Grok Bot - Hedge Fund Research Desk.pdf`**

These are the original pure-research swarm documents.  
They are kept only as historical backup.  

**Do not load, run, or point any bot at these files.**  
They are not part of the active system.

---

## Quick Start

1. Point your bot at this repository.
2. Tell it to follow **`Grok Bot - Flagship Growth Desk.txt`** (and `SETUP.md` if needed).
3. Explicitly instruct it to ignore the Hedge Fund Research Desk files.
4. Seed the workspace with `watchlist.csv` and `model_portfolio.json`.
5. Run the overnight research + weekly Flagship cycle.
6. You decide and execute.

See `changes/CHANGES.md` for the full record of the cut from 13 bots to the current 9-bot design.
