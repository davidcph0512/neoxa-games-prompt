# Prompt: Forging & Smelting Recipes (Section 3.2)

Act as a Game Economy Designer documenting the orbital foundry smelting system for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. Canonical numbers: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`.

## Core Rules

1. Raw ores cannot be sold for NMG directly.
2. Catalyst NMG: **95% burned on-chain | 5% recycled to Smelting Reward Reserve**.
3. NMG rewards paid from **Smelting Reward Reserve** (8,400,000 NMG — 40% of 21M cap). **Never minted.**
4. **Effective_Reward = Base_Reward × Emission_Multiplier** (see scaling table below).
5. If Reserve below 5%, rewards pause until governance replenishment.

## Tutorial Catalyst Subsidy

| Parameter | Value |
|-----------|-------|
| Free subsidized smelts | 3 per account |
| Covered recipe | Bronze Ingot only (0.10 NMG catalyst each) |
| Player cost | 0 NMG |
| Funding | Tutorial Subsidy Pool (50,000 NMG cap) |
| After 3 smelts | Normal catalyst required |

## Smelting Recipe Table

| Ingot | Inputs | Catalyst Burn | Base Reward | Base Net |
|-------|--------|---------------|-------------|----------|
| Bronze | 100 Copper + 50 Coal | 0.10 NMG | 1.20 NMG | +1.10 |
| Iron | 150 Iron + 80 Coal | 0.50 NMG | 3.50 NMG | +3.00 |
| Mithril | 80 Mithril + 10 Iron + 100 Coal | 2.00 NMG | 15.00 NMG | +13.00 |
| Astral | 50 Star-Element + 150 Mithril + 200 Coal | 10.00 NMG | 85.00 NMG | +75.00 |

## Emission Scaling

| Reserve Remaining | Multiplier | Message |
|-------------------|------------|---------|
| 100%–50% | 1.0× | Normal operations |
| 50%–20% | 0.75× | Industrial output adjusted |
| 20%–5% | 0.50× | Reserve conservation mode |
| Below 5% | Pause | Awaiting governance replenishment |

## Smelting Flow

1. Validate ores and catalyst (or tutorial subsidy eligibility).
2. Deduct ores (atomic).
3. Execute catalyst burn: 95% on-chain burn, 5% to Reserve (or Tutorial Pool for subsidies).
4. On confirmation: credit Effective_Reward from Reward Reserve.
5. On burn failure: rollback ore deduction.

## Withdrawal & Guardrails

- Min withdrawal: 1 NMG | Daily cap: 100 NMG | New account cooldown: 24h
- Global smelt cap: 10,000 smelts/server/day

## Your Task

Write a complete smelting design document in English covering validation, subsidy flow, emission scaling, Reserve accounting, failure handling, and UI (show Effective_Reward preview and emission multiplier).
