# Prompt: Game Prototype Economy Calibration & NMG Balance Audit

Act as a Lead Game Economist and Frontend Engineer auditing the **Terra-Forge: The Deep Core** browser prototype (`web/game.html`) against canonical v2.2.0 numbers.

**Important:** English only. No NFTs. Canonical source: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`. Do not invent numbers — use canonical values only.

---

## Problem Statement

Playtesters report earning far too much NMG from minimal AFK time (e.g., **1,265+ NMG in seconds/minutes**). Canonical design expects **~3.6 NMG total** from the 3 tutorial Bronze smelts, and **~19 hours** of Surface mining before a F2P player can afford their first uns subsidized Bronze smelt.

The prototype is **not broken at the reward layer** — Bronze still pays **1.20 NMG base** correctly. The bug is **upstream**: mining throughput and smelting ore costs are orders of magnitude too cheap, enabling hundreds of smelts per hour instead of ~3 per day per active smelter in the runway model.

---

## Root Cause Analysis (Prototype vs Canonical)

### A. Mining Speed — Wrong Time Unit

| | Prototype (`game.html`) | Canonical (§3.1, `05-mining-speed-equation.md`) |
|--|-------------------------|------------------------------------------------|
| Rate display | `0.5 ore/sec` (Common Biotech) | **Φ_base = 10 ores/hour** total raw ore |
| Common L1 Surface D=0 | ~1,800 ores/hour effective | **~11.5 ores/hour** |
| Error magnitude | **~156× too fast** | — |

**Fix rule:** All mining rates must be expressed in **ores per hour**, derived from:

```
Φ = 10 × (1 + 0.15 × L) × (1 − 0.80 × D) × γ_rarity × γ_depth
```

Worked example (Common, L=1, Surface, D=0): **11.5 ores/hour**.

Do NOT use `ore/sec` as the primary unit. If displaying per-second for UX animation, derive it as `Φ / 3600`.

### B. Smelting Recipe Inputs — Wrong Quantities

| Ingot | Prototype inputs | Canonical inputs | Error |
|-------|------------------|------------------|-------|
| Bronze | 5 Copper + 2 Coal | **100 Copper + 50 Coal** | **~20× too cheap** |
| Iron | 5 Iron + 3 Coal | **150 Iron + 80 Coal** | **~30× too cheap** |
| Mithril | 10 Mithril + 5 Coal | **80 Mithril + 10 Iron + 100 Coal** | Wrong recipe |
| Astral | 20 Star + 10 Mithril | **50 Star-Element + 150 Mithril + 200 Coal** | Wrong recipe |

Catalyst fees and base rewards in the prototype **match canonical** — only inputs and mining speed are wrong.

### C. Combined Effect — Why 1,265 NMG Happens

With wrong numbers, a single Common miner on Surface produces enough ores for Bronze every **~14 seconds** instead of **~19 hours**.

```
1,265.6 NMG ÷ 1.20 NMG per Bronze ≈ 1,055 smelts
```

At ~14 seconds per smelt cycle, that is achievable in **~4 hours** of idle play — or much faster with multiple miners and active clicking. This is **economically catastrophic** vs the 8.4M Reserve runway model (7M max Bronze smelts over years, not hours).

### D. What Is NOT the Bug

- NMG reward amounts (1.20 / 3.50 / 15.00 / 85.00) — **correct**
- Tutorial subsidy count (3 free Bronze) — **correct**
- Emission multiplier tiers (1.0× / 0.75× / 0.50× / pause) — **correct logic**
- Starter Gold (500) — **correct**

---

## Calibration Requirements

### 1. Mining Tick

- Base throughput: **10 ores/hour** before modifiers
- Apply canonical `γ_rarity` and `γ_depth` multipliers
- Apply durability penalty: `(1 − 0.80 × D)` where D = 1 − (durability/100)
- Apply fatigue: +0.10/hour; halt mining at fatigue = 1.0
- Durability loss: **5 per hour** mining (not per second)
- Ore drops: use canonical zone percentages from `16-economy-numbers-bible.md` §6

### 2. Smelting Recipes

Replace all `RECIPES` inputs with canonical values:

| Ingot | Inputs | Catalyst | Base Reward |
|-------|--------|----------|-------------|
| Bronze | 100 Copper + 50 Coal | 0.10 NMG | 1.20 |
| Iron | 150 Iron + 80 Coal | 0.50 NMG | 3.50 |
| Mithril | 80 Mithril + 10 Iron + 100 Coal | 2.00 NMG | 15.00 |
| Astral | 50 Star-Element + 150 Mithril + 200 Coal | 10.00 NMG | 85.00 |

### 3. Expected Player Timelines (Acceptance Tests)

After calibration, verify these milestones:

| Milestone | Expected time (F2P, 1 Common miner, Surface) |
|-----------|-----------------------------------------------|
| First Bronze smelt (materials only) | **~19 hours** |
| 3 tutorial Bronze smelts complete | **~57 hours** mining + smelting |
| Total tutorial NMG earned | **~3.6 NMG** (3 × 1.20 at 1.0× emission) |
| NMG after 5 minutes AFK (no subsidies spent) | **~0 NMG** (still accumulating ores) |
| NMG after 1 hour AFK | **~0 NMG** (still accumulating ores) |

### 4. UI Honesty

- Display mining rate as **ores/hour**, not ores/sec
- Show **Effective Reward = Base × Emission Multiplier** on every recipe card
- Show ore progress toward next smelt (e.g., "45/100 Copper")
- Add tooltip: "NMG is earned only through smelting, not mining. Mining collects raw ores."

### 5. Guardrails (Prototype — Local Simulation)

Even in the browser prototype, simulate these server-side rules:

| Guardrail | Value | Prototype behavior |
|-----------|-------|-------------------|
| Global smelt cap | 10,000/day/server | Show warning if exceeded (single-player: cap at 50/day for demo) |
| Daily withdraw cap | 100 NMG/account | Enforce on withdraw button (Phase 2) |
| Reserve depletion | Emission scaling | Already implemented — keep |

---

## Deliverables

1. **Calibration checklist** — table mapping every prototype constant to its canonical source with pass/fail status.
2. **Acceptance test script** — step-by-step playtest: new account → hire miner → dispatch → wait X hours → expected ore counts → smelt → expected NMG.
3. **Player-facing FAQ entry:** "Why did I earn so much NMG in the demo?" → explain prototype was miscalibrated; production uses canonical pacing.
4. **Developer note:** Any demo/prototype mode that uses accelerated rates MUST be labeled **"Demo Speed — Not Production Economics"** and must never be deployed to the public URL without a clear banner.

All numbers must match `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md` exactly.
