# GrokBot-Trading

**Primary system: Flagship Growth Desk (v1.1)**

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
- Self-improving (with your approval)
- You still execute every trade manually

**Goal: stay profitable.**  
The architecture exists to support that goal — not to create complexity for its own sake. Use only the pieces that help. Ignore or disable anything that feels overboard.

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

Keep it simple. Focus on clear high-conviction ideas and sensible position management. Profitability first.
