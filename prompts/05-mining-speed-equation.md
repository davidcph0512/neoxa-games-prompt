# Prompt: Core Gameplay Loop — Mining Speed Equation (Section 3.1)

Act as a Game Systems Designer documenting the ore extraction mechanics for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. Canonical numbers: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`.

## Mining Speed Formula

**Φ = Φ_base × (1 + α × L_tool) × (1 − β × D) × γ_rarity × γ_depth**

| Parameter | Value |
|-----------|-------|
| Φ_base | 10 units/hour (total raw ore) |
| α | 0.15 |
| β | 0.80 |
| L_tool | 1 or 2 |

### γ_rarity: Common 1.0 | Rare 1.25 | Epic 1.60 | Legendary 2.20

### γ_depth: Surface 1.0 | Mid-Fracture 1.3 | Deep Core 1.6

## Ore Drop Table (% of total ore units)

| Zone | Copper | Iron | Coal | Mithril | Star-Element |
|------|--------|------|------|---------|--------------|
| Surface | 45% | 30% | 25% | 0% | 0% |
| Mid-Fracture | 30% | 25% | 25% | 15% | 5% |
| Deep Core | 15% | 20% | 25% | 30% | 10% |

## Fatigue

- +0.10 per hour mining; halt at D = 1.0
- Camp Rest: **50 Gold**
- Instant Cooling: **0.5 NMG** burned on-chain

## Durability

- Max 100; −5 per hour mining; repair **10 Gold per 10 points**

## New Player Entry

- **500 Starter Gold** on account creation — no NMG required to begin
- Hire Common Biotech Miner for **200 Gold**

## Your Task

Write a complete mining system design document in English covering real-time ticks, zone selection, ore splits, fatigue, durability, and worked examples using canonical numbers only.
