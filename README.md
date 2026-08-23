# GrokBot-Trading

**Primary system: Flagship Growth Desk (v1.2 Lean)**

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
- Measured self-improvement (with your approval)
- You still execute every trade manually

Version 1.2 is the lean build: 8 bots instead of 13, combined research coverage, optional lightweight graph context. Still robust — not stripped down to the point of losing useful signal.

Supporting files:
- `SETUP.md` — first-weekend checklist
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

Keep it usable. Focus on clear high-conviction ideas and sensible position management.
