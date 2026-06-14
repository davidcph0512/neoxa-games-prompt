# Terra-Forge: The Deep Core — Economy Numbers Bible

**Version:** 2.2.0 | **Status:** Canonical | **Language:** English only

Single authoritative numeric reference for developers, economists, and investors. All values match `.whitepaper` v2.2.0.

---

## 1. External Price References

| Parameter | Value | Notes |
|-----------|-------|-------|
| NEOX / USDC | 0.00008 USDC per NEOX | Ops-updated external reference |
| USDC / NEOX | 12,500 NEOX per 1 USDC | Inverse |
| 100 USDC | 1,250,000 NEOX | Verified: 1,250,000 × 0.00008 = 100 |
| Smartnode stake | 1,000,000 NEOX | ≈ $80 USDC at reference price |
| DEX swap fee | 1.5% | neoxa.exchange NMG/NEOX pair |

**Rule:** NMG is NOT pegged to NEOX. Market price floats.

---

## 2. NMG Supply Allocation (Hard Cap: 21,000,000)

| Allocation | NMG | % | Purpose |
|------------|-----|---|---------|
| Smelting Reward Reserve | 8,400,000 | 40% | All ingot redemption rewards (scaled) |
| Game Treasury (NMG) | 4,200,000 | 20% | Ops, community, Reserve replenishment |
| Liquidity Bootstrap | 2,100,000 | 10% | Initial DEX / market making |
| Development Fund | 3,150,000 | 15% | Vested team & development |
| Community & Ecosystem | 3,150,000 | 15% | Grants, events, partnerships |
| **Total** | **21,000,000** | **100%** | Fixed forever — never minted beyond |

**Sub-account:** Tutorial Subsidy Pool — 50,000 NMG cap (from Community allocation)

**Replenishment:** Governance Treasury → Reserve (max 10%/quarter) | Catalyst recycle 5% → Reserve

---

## 3. Currency Conversion

| Conversion | Rate | Direction |
|------------|------|-----------|
| NMG → Gold | 1 NMG = 250 Gold | One-way; irreversible |
| Gold → NMG | Forbidden | — |
| NMG → NEOX | Market price | Floating on neoxa.exchange |
| NEOX → USDC | 0.00008 USDC | External reference |

---

## 4. New Player Economics

| Parameter | Value |
|-----------|-------|
| Starter Gold | 500 (one-time) |
| Common Biotech hire | 200 Gold |
| Tutorial subsidies | 3 free Bronze smelts |
| Subsidy cost covered | 0.10 NMG each (Tutorial Pool) |
| Expected F2P NMG | ~3.6 NMG (3 × 1.20 base) |
| Wallet required to start | No |
| First withdraw cooldown | 24 hours |

---

## 5. Mining Speed

**Φ = 10 × (1 + 0.15 × L) × (1 − 0.80 × D) × γ_rarity × γ_depth**

| γ_rarity | Common 1.0 | Rare 1.25 | Epic 1.60 | Legendary 2.20 |
| γ_depth | Surface 1.0 | Mid-Fracture 1.3 | Deep Core 1.6 |

**Examples:** Common L1 Surface D=0 → 11.5 ores/hr | Legendary L2 Deep D=0.5 → 27.46 ores/hr

---

## 6. Ore Drops (% of total)

| Zone | Copper | Iron | Coal | Mithril | Star-Element |
|------|--------|------|------|---------|--------------|
| Surface | 45% | 30% | 25% | 0% | 0% |
| Mid-Fracture | 30% | 25% | 25% | 15% | 5% |
| Deep Core | 15% | 20% | 25% | 30% | 10% |

---

## 7. Fatigue & Durability

| Parameter | Value |
|-----------|-------|
| Fatigue gain | +0.10/hour mining |
| Camp Rest | 50 Gold |
| Instant Cooling | 0.5 NMG burn |
| Durability max | 100 |
| Durability loss | 5/hour |
| Repair | 10 Gold per 10 points |

---

## 8. Guild Miner Costs

| Rarity | Class | Cost |
|--------|-------|------|
| Common | Biotech | 200 Gold |
| Rare | Biotech | 800 Gold |
| Epic | Cyborg | 50 NMG deposit |
| Legendary | Cyborg | 200 NMG deposit (500/epoch) |

---

## 9. Smelting Recipes

| Ingot | Inputs | Catalyst | Base Reward | Base Net |
|-------|--------|----------|-------------|----------|
| Bronze | 100 Copper + 50 Coal | 0.10 NMG | 1.20 | +1.10 |
| Iron | 150 Iron + 80 Coal | 0.50 NMG | 3.50 | +3.00 |
| Mithril | 80 Mithril + 10 Iron + 100 Coal | 2.00 NMG | 15.00 | +13.00 |
| Astral | 50 Star-Element + 150 Mithril + 200 Coal | 10.00 NMG | 85.00 | +75.00 |

**Effective Reward = Base Reward × Emission Multiplier**  
**Catalyst:** 95% burned | 5% recycled to Reserve

---

## 10. Upgrades

L=1→2: **1.50 NMG + 25 Gold** (1.20 NMG burned, 0.30 to Treasury)

---

## 11. Withdrawal & Guardrails

| Rule | Value |
|------|-------|
| Min withdrawal | 1 NMG |
| Daily cap | 100 NMG/account |
| Global smelt cap | 10,000/server/day |
| Reserve alert | 20% remaining |
| P_floor bootstrap | 0.08 NEOX/NMG |

---

## 12. Emission Scaling

| Reserve Remaining | Multiplier |
|-------------------|------------|
| 100%–50% | 1.0× |
| 50%–20% | 0.75× |
| 20%–5% | 0.50× |
| Below 5% | Pause |

---

## 13. Reserve Runway

- Max Bronze smelts: **7,000,000**
- Example: 1,000 smelters × 3/day = **~6.4 years** (before scaling)
- Sustainable for **years, not infinite**

---

## 14. Win Matrix

| Class | Crypto Upfront? | Path |
|-------|-----------------|------|
| Active F2P | No | 500 Gold → mine → 3 subsidized Bronze → ~3.6 NMG |
| Active invested | Optional | Deposit → upgrade → higher ingots |
| Capital Provider | Yes | Rental 60/40 → passive ore |
| Liquidity Provider | Yes | 1.5% DEX fees |
| Smartnode Operator | Yes | 45% block rewards |

---

## One-Page Sustainability Summary

Rewards never mint — they debit the 8.4M Reserve. Catalyst burns remove 95% of NMG permanently while recycling 5% back. Emission scaling prevents cliff depletion. Every player class has a non-zero win path. NMG/NEOX floats — no peg. The economy is designed for multi-year operation with honest transparency about finite Reserve capacity.
