# Prompt: Economy Numbers Bible — Canonical Numeric Reference

Act as a Lead Game Economist producing the **single authoritative numeric reference** for **Terra-Forge: The Deep Core**. All numbers below are canonical. Do not invent conflicting values.

**Global rules:** English only. No NFTs. Guild Miners are in-game database assets only. NMG/NEOX is a floating market pair — never a fixed peg.

**Source of truth:** `.whitepaper` v2.2.0

---

## 1. External Price References

| Parameter | Value | Notes |
|-----------|-------|-------|
| NEOX / USDC | 0.00008 USDC per NEOX | External reference; updated periodically by ops |
| USDC / NEOX | 12,500 NEOX per 1 USDC | Inverse |
| 100 USDC | 1,250,000 NEOX | Sanity check: 1,250,000 × 0.00008 = 100 ✓ |
| Smartnode stake | 1,000,000 NEOX | ≈ $80 USDC at reference price |
| DEX swap fee | 1.5% | neoxa.exchange NMG/NEOX pair |

**Critical rule:** NMG is NOT pegged to NEOX. Market price floats. Hard pegging would break the economy due to net-positive smelting rewards.

---

## 2. NMG Supply (Hard Cap: 21,000,000 — never minted beyond this)

| Allocation | NMG | % | Purpose |
|------------|-----|---|---------|
| Smelting Reward Reserve | 8,400,000 | 40% | Pays ALL ingot redemption rewards (scaled) |
| Game Treasury (NMG) | 4,200,000 | 20% | Ops, community; Reserve replenishment source |
| Liquidity Bootstrap | 2,100,000 | 10% | Initial DEX / market making |
| Development Fund | 3,150,000 | 15% | Vested team & development |
| Community & Ecosystem | 3,150,000 | 15% | Grants, events, partnerships |
| **Total** | **21,000,000** | **100%** | Fixed forever |

### Sub-accounts

| Sub-account | Cap | Purpose |
|-------------|-----|---------|
| Tutorial Subsidy Pool | 50,000 NMG | Free Bronze catalyst burns for new players (from Community allocation) |

**Reward payout rule:** Smelting credits NMG from Smelting Reward Reserve only. Never implicit mint. Emission scaling applies (see §16). Below 5% Reserve, rewards pause.

**Replenishment:**
- Governance: Game Treasury → Reserve (max 10% of Treasury per quarter)
- Catalyst recycle: 5% of catalyst burns → Reserve; 95% burned on-chain

---

## 3. Currency Conversion

| Conversion | Rate | Direction |
|------------|------|-----------|
| NMG → Gold (deposit) | 1 NMG = 250 Gold | One-way only; irreversible |
| Gold → NMG | — | **Forbidden** |
| NMG → NEOX | Market price on neoxa.exchange | Floating; not fixed |
| NEOX → USDC | 0.00008 USDC per NEOX | External reference |

---

## 4. New Player & Entry Economics

| Parameter | Value |
|-----------|-------|
| Starter Gold (one-time per account) | 500 Gold |
| Common Biotech Miner hire cost | 200 Gold |
| Tutorial Catalyst Subsidies | 3 free Bronze smelts per account |
| Subsidy catalyst cost covered | 0.10 NMG each (from Tutorial Subsidy Pool) |
| Expected F2P NMG from subsidies | ~3.6 NMG (3 × 1.20 base reward, before scaling) |
| First playable loop without wallet | Yes — subsidies cover catalyst gap |
| Gold as F2P win layer | Rank, guild standing, marketplace, ore sales |
| NMG as withdrawal layer | Optional; requires wallet + 24h cooldown for first withdraw |

---

## 5. Mining Speed Equation

**Formula:** Φ = Φ_base × (1 + α × L_tool) × (1 − β × D) × γ_rarity × γ_depth

| Symbol | Value |
|--------|-------|
| Φ_base | 10 units/hour (total raw ore) |
| α | 0.15 |
| β | 0.80 |
| L_tool | 1 or 2 (max) |

### γ_rarity

| Tier | Multiplier |
|------|------------|
| Common | 1.0 |
| Rare | 1.25 |
| Epic | 1.60 |
| Legendary | 2.20 |

### γ_depth (mining zone)

| Zone | Multiplier |
|------|------------|
| Surface | 1.0 |
| Mid-Fracture | 1.3 |
| Deep Core | 1.6 |

### Worked Examples

| Config | Φ (ores/hr) |
|--------|-------------|
| Common, L=1, D=0, Surface | 11.5 |
| Legendary, L=2, D=0.5, Deep Core | 27.46 |
| Any miner, D=1.0 | 0 (halted) |

---

## 6. Ore Drop Table (% of total ore units)

| Zone | Copper | Iron | Coal | Mithril | Star-Element |
|------|--------|------|------|---------|--------------|
| Surface | 45% | 30% | 25% | 0% | 0% |
| Mid-Fracture | 30% | 25% | 25% | 15% | 5% |
| Deep Core | 15% | 20% | 25% | 30% | 10% |

---

## 7. Fatigue & Durability

| Parameter | Value |
|-----------|-------|
| Fatigue gain | +0.10 per hour mining |
| Fatigue halt | D = 1.0 → Φ = 0 |
| Camp Rest cost | 50 Gold (resets D to 0) |
| Instant Cooling cost | 0.5 NMG burned on-chain (resets D to 0) |
| Durability max | 100 points |
| Durability loss | 5 per hour mining |
| Repair cost | 10 Gold per 10 durability restored |

---

## 8. Guild Miner Costs (In-Game)

| Rarity | Class | Cost | Supply Limit |
|--------|-------|------|--------------|
| Common | Biotech | 200 Gold | Unlimited |
| Rare | Biotech | 800 Gold | Unlimited |
| Epic | Cyborg | 50 NMG (via deposit → Gold) | Unlimited |
| Legendary | Cyborg | 200 NMG (via deposit → Gold) | 500 per server epoch |

---

## 9. Smelting Recipes

| Ingot | Inputs | Catalyst Burn | Base Reward | Base Net |
|-------|--------|---------------|-------------|----------|
| Bronze | 100 Copper + 50 Coal | 0.10 NMG | 1.20 NMG | +1.10 |
| Iron | 150 Iron + 80 Coal | 0.50 NMG | 3.50 NMG | +3.00 |
| Mithril | 80 Mithril + 10 Iron + 100 Coal | 2.00 NMG | 15.00 NMG | +13.00 |
| Astral | 50 Star-Element + 150 Mithril + 200 Coal | 10.00 NMG | 85.00 NMG | +75.00 |

**Effective Reward** = Base Reward × Emission Multiplier (see §16)

**Catalyst split:** 95% burned on-chain | 5% recycled to Smelting Reward Reserve

**Reward source:** Smelting Reward Reserve (not minted).

**Tutorial subsidy:** First 3 Bronze smelts per account — catalyst paid from Tutorial Subsidy Pool; player pays 0 NMG.

---

## 10. Tool Upgrade Costs

**Formula:** Cost = (L)² × φ × NMG + (L)^1.5 × θ × Gold  
φ = 1.50 | θ = 25.00 | Max L = 2

| Upgrade | NMG | Gold | NMG Burned (80%) | Treasury (20%) |
|---------|-----|------|------------------|----------------|
| L=1→2 | 1.50 | 25 | 1.20 | 0.30 |

---

## 11. Withdrawal Limits

| Parameter | Value |
|-----------|-------|
| Minimum withdrawal | 1 NMG |
| Daily cap per account | 100 NMG (governance tunable) |
| New account cooldown | 24 hours before first withdrawal |
| Withdrawal source wallet | Smelting Reward Reserve (L1) |

---

## 12. P2P Marketplace

| Parameter | Value |
|-----------|-------|
| Trade fee | 2% (Gold sink → Game Treasury) |
| Escrow timeout | 1 hour (auto-refund) |
| Accepted currencies | Gold, in-game NMG balance |

---

## 13. Miner Rental (Server-Enforced Escrow)

| Parameter | Value |
|-----------|-------|
| Enforcement | Smartnode game servers — NOT on-chain smart contracts |
| Default split example | 60% Owner / 40% Renter |
| Force-recall grace | 24 hours renter inactivity |
| Deposit | Optional Gold escrow (owner-configurable) |

**Not trustless.** Described accurately as server-enforced escrow.

---

## 14. Treasury & Buyback

### Two Treasury Buckets

| Bucket | Denomination | Funding |
|--------|--------------|---------|
| Game Treasury (NMG) | NMG | 20% of upgrade NMG; marketplace fees; can replenish Reserve |
| Buyback Reserve | NEOX / USDC | Periodic Treasury NMG sales on DEX; direct stablecoin |

### Floor Price

P_floor = Σ(recipe_weight × catalyst_NMG / net_NMG) × P_NMG_MA

- P_NMG_MA = 7-day moving average NMG/NEOX on neoxa.exchange
- Bootstrap P_floor = **0.08 NEOX per NMG** (recalculated weekly)

### Buyback Formula (dimensionally correct)

**Trigger:** P_NMG < P_floor AND R_treasury > 0

**Q_buyback** = min( R_treasury / (δ × P_NMG),  Ψ × Circulating_NMG × (P_floor − P_NMG) / P_floor )

| Symbol | Value | Unit |
|--------|-------|------|
| Q_buyback | output | NMG to buy and burn |
| R_treasury | Buyback Reserve | NEOX |
| P_NMG | spot price | NEOX per NMG |
| P_floor | industrial floor | NEOX per NMG |
| δ | 10 | max 10% R spent per window |
| Ψ | 0.05 | intensity (governance tunable) |
| Circulating_NMG | estimate | NMG in wallets + unclaimed Reserve |

Recovery window: 1 hour cooldown between batches.

---

## 15. Sustainability Guardrails

| Guardrail | Value | Purpose |
|-----------|-------|---------|
| Daily withdraw cap | 100 NMG / account | Prevent Reserve drain spikes |
| Global daily smelt cap | 10,000 smelts / server | Rate-limit extraction |
| Catalyst burn recycle | 5% → Reserve, 95% burned | Partial sustainability loop |
| Reserve runway alert | Ops alert at 20% remaining | Trigger governance review |
| New account withdraw cooldown | 24 hours | Sybil protection |
| Treasury → Reserve replenishment | Max 10% of Treasury / quarter | Controlled Reserve refill |

---

## 16. Dynamic Reserve Emission Scaling

**Effective_Reward** = Base_Reward × Emission_Multiplier

| Reserve Remaining (% of 8.4M) | Emission Multiplier | Player Message |
|-------------------------------|---------------------|----------------|
| 100% – 50% | 1.0× | Normal operations |
| 50% – 20% | 0.75× | Industrial output adjusted |
| 20% – 5% | 0.50× | Reserve conservation mode |
| Below 5% | 0× (pause) | Awaiting governance replenishment |

Reserve_Initial = 8,400,000 NMG

---

## 17. Reserve Runway Model

| Metric | Value |
|--------|-------|
| Reserve initial | 8,400,000 NMG |
| Theoretical max Bronze smelts | 7,000,000 (8.4M / 1.20 base reward) |
| Example DAU smelters | 1,000 |
| Example smelts per smelter per day | 3 Bronze |
| Daily smelt volume | 3,000 |
| Runway at Bronze-only (no scaling) | ~6.4 years (7,000,000 / 3,000 / 365) |
| Higher-tier drain multiplier vs Bronze | Iron ~2.9×, Mithril ~12.5×, Astral ~70.8× reward drain |

Emission scaling and guardrails extend effective runway. Honest expectation: **sustainable for years, not infinite**.

---

## 18. Everyone Winnable — Win Matrix

| Player Class | Primary Win | Crypto Upfront? | Minimum Viable Path |
|--------------|-------------|-----------------|---------------------|
| Active (F2P) | Gold + tutorial NMG + ore sales | No | 500 Gold → mine → 3 subsidized Bronze → ~3.6 NMG + P2P ore Gold |
| Active (invested) | Smelting net NMG + withdraw | Optional | Deposit NMG → faster progression → higher ingots |
| Capital Provider | Rental ore share → smelt/sell | Yes (50–200 NMG) | List Legendary 60/40 → passive ore income |
| Liquidity Provider | 1.5% DEX swap fees | Yes (LP stake) | Independent of game; wins from volume |
| Smartnode Operator | 45% L1 block rewards | Yes (1M NEOX) | Infrastructure yield; secures player state |

**Marketing message:** Everyone can win differently — each class has a designed non-zero path.

---

## 19. ROI Sanity Check (Reference Scenario)

**Setup:** Common Biotech, Surface, L=1, D=0 → 11.5 ores/hr  
Split: ~5.2 Copper, ~3.5 Iron, ~2.9 Coal per hour

**Bronze Ingot** needs 100 Copper + 50 Coal ≈ ~19 hours mining (Surface)  
First 3 smelts: subsidized catalyst (0 NMG cost) → +1.20 NMG each from Reserve

At P_NMG = 0.10 NEOX, 1 NEOX = $0.00008:
- Net per bronze ≈ 1.10 NMG × 0.10 NEOX × $0.00008 ≈ **$0.0000088**
- Value scales with market P_NMG; F2P also wins Gold via ore sales without withdrawal

---

## Your Task

Using ONLY the numbers in this document, produce:

1. A formatted Economy Numbers Bible table suitable for developers and investors.
2. A one-page sustainability summary explaining Reserve accounting, emission scaling, catalyst recycle, and win paths for all player classes.
3. Flag any feature request that would require changing a canonical number — changes must update `.whitepaper` v2.2.0 first.

## Deliverables

Complete numeric reference document in English. No NFTs. No code. All values must match this prompt and `.whitepaper` v2.2.0 exactly.
