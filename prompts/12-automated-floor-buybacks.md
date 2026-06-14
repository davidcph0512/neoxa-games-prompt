# Prompt: Anti-Inflationary Token Sinks — Automated Liquidity Floor Buybacks (Section 5.2)

Act as a DeFi Protocol Economist documenting the automated treasury buyback system for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. Canonical numbers: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`. Include catalyst recycle (5%) and sustainability guardrails.

## Two Treasury Buckets

| Bucket | Currency | Purpose |
|--------|----------|---------|
| Game Treasury (NMG) | NMG | Receives 20% of upgrade NMG; marketplace fees |
| Buyback Reserve | NEOX / USDC | Funds market buybacks; fed by periodic Treasury NMG sales on DEX + stablecoin allocations |

## External Reference

1 NEOX = 0.00008 USDC (ops-updated). NMG/NEOX is a **floating market price** — not pegged.

## Floor Price (P_floor)

P_floor = Σ(recipe_weight × catalyst_NMG / net_NMG) × P_NMG_MA

- P_NMG_MA = 7-day moving average NMG/NEOX on neoxa.exchange
- Bootstrap: **P_floor = 0.08 NEOX per NMG** (recalculated weekly)

## Buyback Trigger

If P_NMG < P_floor AND R_treasury > 0 → execute buyback.

## Buyback Formula (Dimensionally Correct)

**Q_buyback = min( R_treasury / (δ × P_NMG),  Ψ × Circulating_NMG × (P_floor − P_NMG) / P_floor )**

| Symbol | Value | Meaning |
|--------|-------|---------|
| Q_buyback | output | NMG quantity to buy and permanently burn |
| R_treasury | NEOX | Buyback Reserve balance |
| P_NMG | NEOX/NMG | Current spot price |
| P_floor | NEOX/NMG | Industrial floor price |
| δ | 10 | Max 10% of R_treasury per 1-hour window |
| Ψ | 0.05 | Buyback intensity (governance tunable) |
| Circulating_NMG | NMG | Wallets + unclaimed Reward Reserve |

Purchased NMG is permanently burned. **1-hour cooldown** between recovery windows.

## Sustainability Guardrails (§5.5)

| Guardrail | Value |
|-----------|-------|
| Daily withdraw cap | 100 NMG / account |
| Global daily smelt cap | 10,000 / server |
| Catalyst recycle | 5% → Reserve, 95% burned |
| Reserve alert | 20% remaining |
| New account withdraw cooldown | 24 hours |
| Treasury → Reserve replenishment | Max 10% / quarter |

## Your Task

Write a complete buyback design document in English explaining treasury funding, the corrected formula, safeguards, admin dashboard, and why floating NMG/NEOX (not peg) is required for sustainability.
