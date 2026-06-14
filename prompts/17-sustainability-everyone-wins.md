# Prompt: Sustainability & Everyone Winnable Framework (Section 4.7 + §5.5–5.6)

Act as a Lead Game Economist and Sustainability Architect for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. Canonical spec: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`. Do not invent numbers — use canonical values only.

---

## Purpose

Write a comprehensive sustainability and "everyone winnable" document that explains how Terra-Forge avoids GameFi 1.0 collapse while ensuring every player class has a designed path to success.

---

## Part 1: Why GameFi 1.0 Failed vs How v2.2 Solves It

Cover these failure modes and Terra-Forge countermeasures:

| GameFi 1.0 Failure | Terra-Forge v2.2 Solution |
|--------------------|---------------------------|
| Salary-token infinite mint | 21M hard cap; Reward Reserve only; no mint |
| Extraction-first cash-out | Sinks (burns, deposits) + withdraw caps + cooldown |
| Peg / arbitrage collapse | Floating NMG/NEOX market; no peg |
| Whale-only economy | 500 Starter Gold + 3 subsidized smelts; Gold F2P layer |
| Reserve cliff depletion | Dynamic emission scaling (1.0× → 0.75× → 0.50× → pause) |
| One winner type | Win Matrix for 5 player paths |

---

## Part 2: Tutorial Catalyst Subsidy (F2P Loop Closure)

Document the free player journey using canonical numbers:

1. Account creation → **500 Starter Gold**
2. Hire Common Biotech Miner → **200 Gold**
3. Mine on Surface (~19 hours for first Bronze materials)
4. Smelt Bronze using **Tutorial Subsidy** (0 NMG cost, up to **3 times**)
5. Earn **~3.6 NMG** in-game (3 × 1.20 base reward)
6. Continue earning via P2P ore sales (Gold), rental (ore share), or deposit NMG for faster path
7. Optional: connect wallet, wait **24h cooldown**, withdraw (min 1 NMG, daily cap 100)

Funding: **Tutorial Subsidy Pool** (50,000 NMG cap from Community allocation).

---

## Part 3: Dynamic Reserve Emission Scaling

Explain why a finite 8.4M Reserve requires scaling:

**Effective_Reward = Base_Reward × Emission_Multiplier**

| Reserve Level | Multiplier | Message |
|---------------|------------|---------|
| 100%–50% | 1.0× | Normal operations |
| 50%–20% | 0.75× | Industrial output adjusted |
| 20%–5% | 0.50× | Reserve conservation mode |
| Below 5% | Pause | Awaiting governance replenishment |

Replenishment: 5% catalyst recycle + governance Treasury transfer (max 10%/quarter).

---

## Part 4: Everyone Winnable — Win Matrix

Write expanded prose for each player class:

### Active Player (F2P)
- **Wins:** Gold, rank, ore trading, ~3.6 tutorial NMG
- **No crypto required**
- **Path:** Starter Gold → mine → subsidized smelt → P2P ore market

### Active Player (Invested)
- **Wins:** Scaled NMG smelting rewards, withdraw to wallet
- **Optional NMG deposit** at 1:250 Gold rate
- **Path:** Deposit → upgrade → deeper zones → higher ingots

### Capital Provider
- **Wins:** Passive ore income from rental splits (e.g., 60/40)
- **Requires:** 50–200 NMG for elite miners
- **Path:** Purchase miner → list for rent → smelt/sell ore share

### Liquidity Provider
- **Wins:** 1.5% DEX swap fees on neoxa.exchange
- **Independent of game** — wins from trading volume

### Smartnode Operator
- **Wins:** 45% of L1 block rewards
- **Requires:** 1,000,000 NEOX stake (~$80 USDC reference)
- **Secures:** All player state and anti-cheat validation

**Key message:** "Everyone can win differently."

---

## Part 5: Gold as F2P Win Layer

Explain that F2P players win meaningfully without ever withdrawing NMG:
- P2P ore marketplace (2% fee, Gold profits)
- Guild rank and leaderboard (Gold wealth)
- Miner rental as renter (40% ore share)
- Progression (Rare miner 800 Gold, deeper zones)

NMG is the **withdrawal layer**, not the only win condition.

---

## Part 6: Sustainability Guardrails

Document all guardrails with purpose:

| Guardrail | Value | Why |
|-----------|-------|-----|
| Daily withdraw cap | 100 NMG | Prevent Reserve spikes |
| Global smelt cap | 10,000/day/server | Rate-limit extraction |
| Catalyst recycle | 5% → Reserve | Partial closed loop |
| Reserve alert | 20% remaining | Governance trigger |
| Withdraw cooldown | 24h new accounts | Sybil protection |
| Treasury replenishment | Max 10%/quarter | Controlled refill |

---

## Part 7: Reserve Runway Transparency

Present honest investor/player expectations:

- 7,000,000 theoretical max Bronze smelts
- ~6.4 years at 3,000 Bronze/day (1,000 smelters × 3)
- Higher tiers drain 7×–71× faster
- Emission scaling extends runway further
- **Sustainable for years, not infinite**

---

## Part 8: Catalyst Burn Split

Every smelting catalyst:
- **95%** burned on-chain (deflationary pressure)
- **5%** recycled to Smelting Reward Reserve (sustainability loop)

Tutorial subsidies burn from Tutorial Subsidy Pool separately.

---

## Deliverables

1. Full sustainability framework document (English, investor + player facing sections).
2. One-page "Everyone Winnable" summary suitable for landing page.
3. Reserve runway chart description (text/table, no code).
4. FAQ: "Can I play for free?" / "Will rewards run out?" / "Is NMG pegged to NEOX?"

All numbers must match `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md` exactly. No NFTs. No code.
