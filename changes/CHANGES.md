# Flagship Growth Desk — Changes Log

This folder records what was removed or combined when moving from the larger 13-bot design to the current lean system, and what was later restored.

---

## Original design (v1.0 / v1.1) — 13 bots

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

Full overnight schedule with many sequential and parallel specialist runs. Graph was a full-time bot. Adaptive Layer was added in v1.1.

---

## Lean cut (v1.2) — 8 bots

**Goal:** Reduce over-building for a solo operator while keeping the system robust and usable.

### What was combined
| Original bots | Became |
|---------------|--------|
| Filings Analyst + Earnings Analyst + Sentiment Analyst + Insider Tracker | **Research Analyst** (one combined overnight brief) |
| Thematic Regime Detector + Catalyst & Power Tracker | **Theme & Catalyst Analyst** |

### What was removed as a full-time bot
| Bot | Status in v1.2 |
|-----|----------------|
| Graph & Spatiotemporal Engineer | Demoted to optional capability only (no dedicated bot). Portfolio Construction / Desk Lead could request simple correlation checks if needed. |

### What stayed
- Macro & Cycle Analyst  
- Valuation & Lynch Classifier  
- Portfolio Construction Bot + full Adaptive Layer (hybrid scale-in/out, conviction weighting, regime sizing, concentration guardrails, smart cash)  
- Calendar Bot  
- Desk Lead / Coordinator  
- Evolve Controller (measured cadence)  
- Concentrated 15–20 name model portfolio  
- Weekly Flagship cycle  
- Theme adaptivity  
- Manual execution only  

### Overnight routine shortened
Fewer sequential specialist starts; Research Analyst runs as one block; lighter parallel macro/theme/valuation pass.

---

## Current design (v1.3 Lean + Graph) — 9 bots

**Change:** Graph & Spatiotemporal Engineer restored as a full modular bot at the operator’s request (cutting-edge correlation / lag / regime / concentration layer).

### Current roster
1. Research Analyst (combined filings + earnings + sentiment + insider)  
2. Macro & Cycle Analyst  
3. Theme & Catalyst Analyst  
4. Valuation & Lynch Classifier  
5. **Graph & Spatiotemporal Engineer** (restored — Hermes-style, modular, reversible, explicit off-switch)  
6. Portfolio Construction Bot + Adaptive Layer  
7. Calendar Bot  
8. Desk Lead / Coordinator  
9. Evolve Controller  

### Still removed / still combined (not restored)
- Separate Filings, Earnings, Sentiment, Insider bots → remain combined as Research Analyst  
- Separate Thematic Regime Detector and Catalyst & Power Tracker → remain combined as Theme & Catalyst Analyst  

### Graph design rules (unchanged philosophy)
- Modular and reversible  
- Never in the critical path  
- Optional confirmation / concentration warnings / regime context only  
- Explicit off-switch in `graph_health.json`  

---

## Summary table

| Version | Bots | Graph status | Research style |
|---------|------|--------------|----------------|
| v1.0 / v1.1 | 13 | Full-time bot | 4 separate research specialists |
| v1.2 Lean | 8 | Optional only (no bot) | Combined Research Analyst |
| **v1.3 Lean + Graph** | **9** | **Full modular bot (restored)** | Combined Research Analyst |

---

## Why this shape

- Solo operator can actually run the desk without drowning in briefs.  
- Adaptive position management and concentrated Flagship book remain.  
- Graph layer is back because it is useful and cutting-edge for concentration and regime context.  
- Combined research still covers filings, earnings, sentiment, and insider without four separate overnight processes.  

Primary system file: `Grok Bot - Flagship Growth Desk.txt` (v1.3).  
Original Hedge Fund Research Desk files remain archived backup only.
