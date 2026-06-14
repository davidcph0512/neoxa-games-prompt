# Terra-Forge: The Deep Core
## Technical Whitepaper & Game Design Document

**Version:** v2.2.0  
**Subtitle:** Ledger Architecture — L1 Native Asset Protocol  
**Language:** English only

**Actions:** [Download PDF](#) · [Launch Forge App](#) · [Back to Home](#)

---

> **Key Stats**
>
> | Metric | Value |
> |--------|-------|
> | NMG Total Supply | 21,000,000 (hard cap) |
> | Smelting Reward Reserve | 8,400,000 (40%) |
> | Starter Gold | 500 per new account |
> | Tutorial Subsidies | 3 free Bronze smelts |
> | Catalyst Recycle | 5% → Reserve · 95% burned |
> | Emission Scaling | Active (1.0× → 0.75× → 0.50× → pause) |
> | DEX Swap Fee | 1.5% to LPs |
> | Smartnode Stake | 1,000,000 NEOX |

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Worldview & Narrative (§1.1, §1.2)](#2-worldview--narrative)
3. [Dual-Token Microeconomics (§2.1–2.4)](#3-dual-token-microeconomics)
4. [Core Gameplay Loop (§3.1–3.10)](#4-core-gameplay-loop)
5. [Revenue Share Framework (§4.1–4.7)](#5-revenue-share-framework)
6. [Anti-Inflationary Sinks (§5.1–5.6)](#6-anti-inflationary-sinks)
7. [Website & Game Interface](#7-website--game-interface)
8. [Glossary](#8-glossary)

---

## 1. Executive Summary

GameFi 1.0 failed because reward tokens were treated as play-to-earn salaries. Players optimized for immediate cash-outs, causing extraction-first behavior, hyperinflation, liquidity drainage, and economic collapse.

**Terra-Forge: The Deep Core** introduces a sustainable GameFi 2.0 paradigm built on industrial mining economics rather than speculative yield farming.

### GameFi 1.0 vs GameFi 2.0

| GameFi 1.0 | GameFi 2.0 (Terra-Forge) |
|------------|--------------------------|
| Unlimited token minting | 21M NMG hard cap — never increased |
| Rewards minted on demand | Rewards paid from pre-allocated Smelting Reward Reserve |
| Single win path: withdraw token | Everyone winnable — Gold, NMG, LP fees, rental, Smartnode yield |
| Peg or fixed exchange rate | Floating NMG/NEOX market on neoxa.exchange |
| NFT-gated assets | Guild Miners are in-game database assets — **no NFTs** |

### Core Design Pillars

- **On-chain NMG** is separated from in-game industrial assets (Gold, Miners, Ores, Ingots).
- **Irreversible deflationary sinks** — deposits, catalyst burns, upgrade burns — remove NMG from circulation.
- **Smelting rewards** are paid from the Smelting Reward Reserve (8,400,000 NMG), never minted beyond the 21M cap.
- **Dynamic emission scaling** prevents Reserve cliff collapse as the pool depletes over years.
- **Gold shields casual players** from crypto volatility; Gold is the F2P win layer.
- **NMG/NEOX** trades at a floating market price — no peg, no fixed exchange rate.
- **Everyone winnable:** each player class (Active, Capital, LP, Smartnode) has a designed non-zero path.

---

## 2. Worldview & Narrative

### §1.1 The Abyssal Descent

**Year 2382.** Deep space arrays detect Planetary Core 9-C — a cold rogue body with no atmosphere, composed of compressed tectonic plates around a radioactive core: **The Obsidian Crust**.

Hyper-pressurized fractures contain super-dense geodes enriched with **NMG (Neox Miner Guild) crystals** — sub-space catalysts for near-instant atomic fusing. The crust takes everything. The guilds take it back.

### §1.2 The Mining Guilds

The player is a **Guild Master** operating orbital command ships. They deploy **Biotech Miners** and **Cyborg MINERs** into deep-core stress zones, extract raw ore, protect it from radiation, and smelt it in orbital foundries.

High-purity **NMG-Ingots** are redeemed through the **Interstellar Merchants Coalition** for liquid NMG. The foundry hums. The guild ledger updates. Another ingot enters the supply chain.

---

## 3. Dual-Token Microeconomics

### §2.1 Economic Flow

```
[ neoxa.exchange ]  NMG / NEOX  (floating market price — NOT a peg)
         |
NMG (L1, 21M cap) --Irreversible Deposit--> Gold (in-game soft currency)
         |                                        |
         |                                        v
         |                                   Guild Miners (in-game DB)
         |                                        |
         |                                        v
         |                                   Raw Ores (in-game DB)
         |                                        |
         |                                   Orbital Forge (NMG catalyst burn)
         |                                   95% burned | 5% recycled to Reserve
         |                                        |
         +<---- Scaled Reward Reserve payout ---- Premium Ingots (in-game DB)
```

### §2.2 Asset Taxonomy

| Asset | Layer | Rules |
|-------|-------|-------|
| **NMG** | Neoxa L1 | Hard cap 21,000,000. Burns on forge/upgrade. Withdrawals from Reward Reserve + player deposits. |
| **Gold** | Game DB | Minted on NMG deposit (one-way). Pays wages, rest, repairs, hire costs. F2P win layer. Never convertible back to NMG. |
| **Guild Miners** | Game DB | Biotech / Cyborg. Rarity: Common → Legendary. **NOT on-chain. NOT NFTs.** Tradable in-game only. |
| **Raw Ores** | Game DB | Copper, Iron, Coal, Mithril, Star-Element. P2P tradable on guild marketplace. |
| **Premium Ingots** | Game DB | Bronze, Iron, Mithril, Astral. Redeem for NMG from Reward Reserve after catalyst burn confirmed. |

### §2.3 NMG Supply Allocation

**Total: 21,000,000 NMG — fixed, never increased.**

| Allocation | NMG Amount | % | Purpose |
|------------|------------|---|---------|
| Smelting Reward Reserve | 8,400,000 | 40% | Pays all ingot redemption rewards |
| Game Treasury (NMG) | 4,200,000 | 20% | Ops, community; replenishment source |
| Liquidity Bootstrap | 2,100,000 | 10% | Initial DEX / market making |
| Development Fund | 3,150,000 | 15% | Vested team & development |
| Community & Ecosystem | 3,150,000 | 15% | Grants, events, partnerships |
| └ Tutorial Subsidy Pool (sub-account) | 50,000 cap | — | Free Bronze catalyst for new players |

**Smelting NEVER mints NMG.** Rewards debit the Smelting Reward Reserve with dynamic emission scaling (see §3.9). When Reserve falls below 5%, rewards pause until governance replenishes from Game Treasury (max 10% of Treasury per quarter).

**Replenishment sources:**
- **Governance:** Game Treasury → Reserve (max 10% per quarter)
- **Catalyst recycle:** 5% of all catalyst burns return to Reserve; 95% burned on-chain

### §2.4 Wallet & Exchange Interoperability

**Supported wallets:** Bitget, Atomic, Neoxa Core GUI, any Neoxa L1 wallet.

**Block confirmation:** ~60 seconds. On-chain actions: deposit, burn, withdrawal.

**External exchange:** [neoxa.exchange](https://neoxa.exchange) — NMG/NEOX pair, **1.5% swap fee** to LPs.

NMG and NEOX have a **floating market price**. There is **NO fixed peg** between them.

**External price reference** (updated periodically by ops):

| Reference | Value |
|-----------|-------|
| 1 NEOX | 0.00008 USDC |
| 100 USDC | 1,250,000 NEOX |

---

## 4. Core Gameplay Loop

### §3.1 New Player Entry (No NMG Required to Start)

Every new account receives **500 Starter Gold** (one-time, in-game only).

Players hire a Common Biotech Miner (200 Gold), dispatch, mine, and smelt using **3 free Tutorial Catalyst Subsidies** (see §3.8). First NMG wallet deposit is optional.

**Gold is the F2P win layer:** leaderboard rank, guild standing, marketplace wealth, and ore-trading profits. NMG is the withdrawal layer — not the only win condition.

### §3.2 NMG → Gold Conversion (Irreversible)

```
1 NMG deposited on-chain = 250 Gold minted in-game
```

Conversion is **one-way**. Gold cannot become NMG.

### §3.3 Mining Speed Equation

Ore extraction rate for miner *i* (total raw ore units per hour):

```
Φ_i = Φ_base × (1 + α × L_tool) × (1 − β × D) × γ_rarity × γ_depth
```

| Parameter | Value |
|-----------|-------|
| Φ_base | 10 units/hour |
| L_tool | {1, 2} (drill level) |
| α | 0.15 |
| D | [0.0, 1.0] (fatigue; +0.10 per hour mining) |
| β | 0.80 (fatigue penalty) |
| γ_rarity | Common 1.0 · Rare 1.25 · Epic 1.60 · Legendary 2.20 |
| γ_depth | Surface 1.0 · Mid-Fracture 1.3 · Deep Core 1.6 |

Fatigue at D = 1.0 halts mining until:
- **Camp Rest:** 50 Gold (resets D to 0)
- **Instant Chemical Cooling:** 0.5 NMG burned on-chain (resets D to 0)

### §3.4 Ore Drop Distribution

Per total ore unit mined:

| Zone | Copper | Iron | Coal | Mithril | Star-Element |
|------|--------|------|------|---------|--------------|
| Surface | 45% | 30% | 25% | 0% | 0% |
| Mid-Fracture | 30% | 25% | 25% | 15% | 5% |
| Deep Core | 15% | 20% | 25% | 30% | 10% |

### §3.5 Durability

- **Durability:** 100 points max
- Mining consumes **5 durability per hour**
- At 0 durability, miner cannot dispatch
- **Repair:** 10 Gold per 10 durability restored

### §3.6 Guild Miner Hire & Purchase

| Rarity | Class | Hire/Purchase Cost | Notes |
|--------|-------|-------------------|-------|
| Common | Biotech | 200 Gold | Starter tier |
| Rare | Biotech | 800 Gold | — |
| Epic | Cyborg | 50 NMG deposit* | *Converted to Gold at 1:250 internally |
| Legendary | Cyborg | 200 NMG deposit* | Limited supply: 500 per server epoch |

### §3.7 Forging & Smelting Recipes

Raw ores cannot be sold for NMG directly. Smelting burns NMG catalyst on-chain (95% burned, 5% recycled to Reserve), then credits scaled NMG reward from the Smelting Reward Reserve.

| Ingot | Inputs | Catalyst Burn | Base Reward | Base Net |
|-------|--------|---------------|-------------|----------|
| Bronze Ingot | 100 Copper + 50 Coal | 0.10 NMG | 1.20 | +1.10 |
| Iron Ingot | 150 Iron + 80 Coal | 0.50 NMG | 3.50 | +3.00 |
| Mithril Ingot | 80 Mithril + 10 Iron + 100 Coal | 2.00 NMG | 15.00 | +13.00 |
| Astral Ingot | 50 Star-Element + 150 Mithril + 200 Coal | 10.00 NMG | 85.00 | +75.00 |

> **Formula — Effective Reward**
>
> ```
> Effective_Reward = Base_Reward × Emission_Multiplier
> ```
>
> Flow: validate materials → deduct ores → on-chain catalyst burn (95/5 split) → credit scaled NMG from Reward Reserve → log event. If burn fails, rollback.

### §3.8 Tutorial Catalyst Subsidy (F2P Smelting Gate)

New players receive **3 free Bronze catalyst subsidies** per account:

- **Covered recipe:** Bronze Ingot only (0.10 NMG catalyst each)
- Player pays **0 NMG**; system burns from Tutorial Subsidy Pool (50,000 NMG cap)
- After 3 subsidized smelts, normal catalyst required (wallet or in-game balance)
- **Expected F2P yield:** ~3.6 NMG in-game (3 × 1.20 base, before emission scaling)

This closes the free entry loop without requiring a wallet deposit.

### §3.9 Dynamic Reserve Emission Scaling

```
Effective_Reward = Base_Reward × Emission_Multiplier
```

**Emission_Multiplier** = f(Reserve_Remaining / Reserve_Initial)

| Reserve Level (% remaining) | Multiplier | Player Message |
|----------------------------|------------|----------------|
| 100% – 50% | **1.0×** | Normal operations |
| 50% – 20% | **0.75×** | Industrial output adjusted |
| 20% – 5% | **0.50×** | Reserve conservation mode |
| Below 5% | **0× (pause)** | Awaiting governance replenishment |

- **Reserve_Initial** = 8,400,000 NMG
- **Reserve_Remaining** tracked on-chain / in DB

The Smeltery Forge UI displays the current emission multiplier before each smelt.

### §3.10 NMG Withdrawal

Players withdraw earned NMG (from smelting redemptions) to their connected wallet. Withdrawals debit in-game balance and transfer from Reward Reserve wallet on L1.

| Rule | Value |
|------|-------|
| Minimum withdrawal | 1 NMG |
| Daily cap per account | 100 NMG (governance tunable) |
| New account cooldown | 24 hours before first withdrawal (Sybil protection) |

---

## 5. Revenue Share Framework

### §4.1 Active Players (Time-Rich, Capital-Poor)

Start with **500 Starter Gold**. Profit via smelting (3 subsidized Bronze first), P2P ore sales for Gold, and renting elite miners via server-enforced marketplace.

### §4.2 Capital Providers (Capital-Rich, Time-Poor)

Purchase elite in-game miners. List them for rent with payout splits (e.g., 60/40). Rental is enforced by game servers with escrow — **not a trustless smart contract**. Owners receive ore share automatically; smelt or sell ores to realize NMG.

### §4.3 Liquidity Providers & Traders

Stake NMG/NEOX on neoxa.exchange. Earn **1.5% swap fees**. Independent of game mechanics.

### §4.4 Smartnode Operators

Stake **1,000,000 NEOX** collateral (~$80 USDC at reference price). Host game DB, matchmaking, and anti-cheat. Receive **45% of L1 block rewards**. Smartnodes are the authoritative source of player state; anti-cheat validates all mining and smelting.

### §4.5 Miner Rental (Server-Enforced Escrow)

- Owner lists miner with split %, duration, optional deposit
- Renter pays deposit (Gold) into escrow
- Ores split each mining tick per agreed ratio
- On expiry or owner force-recall (after 24h renter inactivity), miner returns
- **NOT trustless** — enforced by Smartnode network consensus

### §4.6 P2P Ore Marketplace

- List ores for Gold or in-game NMG balance (not on-chain until withdrawal)
- **2% fee** on trades → Game Treasury (Gold sink)
- Escrow holds goods until buyer confirms or 1-hour timeout refunds

### §4.7 Everyone Winnable — Win Matrix

Everyone can win differently. Each class has a designed non-zero path:

| Player Class | Primary Win | Crypto Upfront? | Minimum Viable Path |
|--------------|-------------|-----------------|---------------------|
| **Active (F2P)** | Gold + tutorial NMG + ore sales | No | 500 Gold → mine → 3 subsidized Bronze → ~3.6 NMG + P2P ore Gold |
| **Active (invested)** | Smelting net NMG + withdraw | Optional | Deposit NMG → faster progression → higher ingots |
| **Capital Provider** | Rental ore share → smelt/sell | Yes (50–200 NMG) | List Legendary 60/40 → passive ore income |
| **Liquidity Provider** | 1.5% DEX swap fees | Yes (LP stake) | Independent of game; wins from trading volume |
| **Smartnode Operator** | 45% L1 block rewards | Yes (1M NEOX) | Infrastructure yield; secures all player state |

---

## 6. Anti-Inflationary Sinks

### §5.1 Upgrade Cost Function

Upgrade drill from L to L+1:

```
Cost = (L)² × φ × NMG + (L)^1.5 × θ × Gold

φ = 1.50   θ = 25.00   Max L = 2
```

**L=1→2:** 1.50 NMG + 25 Gold

- **80%** of NMG (1.20) → on-chain burn
- **20%** of NMG (0.30) → Game Treasury (NMG)

### §5.2 Treasury & Buyback Architecture

Two treasury buckets:

| Bucket | Currency | Purpose |
|--------|----------|---------|
| **A) Game Treasury** | NMG | Receives 20% of upgrade NMG, marketplace fees. Can replenish Reserve (max 10% per quarter via governance). |
| **B) Buyback Reserve** | NEOX/USDC | Funded by periodic sale of Treasury NMG on DEX and direct stablecoin allocations. |

### §5.3 Floor Price (P_floor)

```
P_floor = Σ(recipe_weight × catalyst_NMG / net_NMG) × P_NMG_MA
```

- **P_NMG_MA** = 7-day moving average of NMG/NEOX on neoxa.exchange
- **Initial bootstrap P_floor** = 0.08 NEOX per NMG (subject to recalculation weekly)

P_floor represents the weighted average industrial cost of producing 1 NMG net profit through smelting, expressed in NEOX per NMG.

### §5.4 Buyback Formula (Dimensionally Corrected)

**Trigger:** P_NMG < P_floor AND R_treasury > 0

```
Q_buyback = min( R_treasury / (δ × P_NMG),  Ψ × Circulating_NMG × (P_floor − P_NMG) / P_floor )
```

| Variable | Definition |
|----------|------------|
| Q_buyback | NMG quantity to buy and permanently burn |
| R_treasury | Buyback Reserve balance (NEOX) |
| P_NMG | Spot NMG price (NEOX per NMG) |
| P_floor | Industrial floor (NEOX per NMG) |
| δ | 10 (max 10% of R_treasury spent per 1-hour recovery window) |
| Ψ | 0.05 (buyback intensity — governance tunable) |
| Circulating_NMG | Estimated NMG in player wallets + Reward Reserve unclaimed |

Purchased NMG is **permanently burned**. Recovery window cooldown: 1 hour.

### §5.5 Sustainability Guardrails

| Guardrail | Value | Purpose |
|-----------|-------|---------|
| Daily withdraw cap | 100 NMG / account | Prevent Reserve drain spikes |
| Global daily smelt cap | 10,000 smelts / server | Rate-limit extraction |
| Catalyst burn recycle | 5% → Reserve, 95% burned | Partial sustainability loop |
| Reserve runway alert | Ops alert at 20% left | Trigger governance review |
| New account withdraw cooldown | 24 hours | Sybil protection |
| Treasury → Reserve replenishment | Max 10% / quarter | Controlled Reserve refill |

### §5.6 Reserve Runway Model

> **Reserve Runway**
>
> | Metric | Value |
> |--------|-------|
> | Theoretical max Bronze smelts | 8,400,000 ÷ 1.20 = **7,000,000** (before scaling) |
> | Example scenario | 1,000 daily active smelters × 3 bronzes/day = 3,000 smelts/day |
> | Estimated runway | **~6.4 years** at Bronze-only, before emission scaling extends further |

Higher-tier ingots drain Reserve **7×–68× faster** per smelt than Bronze. Emission scaling (§3.9) and guardrails (§5.5) are mandatory for multi-year sustainability.

**Honest expectation:** sustainable for years, not infinite, unless recycling and governance replenishment keep pace with player growth.

---

## 7. Website & Game Interface

**Visual direction:** Industrial steampunk sci-fi. Dark mode. Colors: `#1A1A24`, `#FF5500`, `#0B0B0F`. Language: English only.

### Portal Sections

| Section | Purpose |
|---------|---------|
| **A) Miner Command Center** | ID, class, rarity, durability, fatigue, dispatch/recall |
| **B) Smeltery Forge** | 4 ingot recipes, catalyst fees, **emission multiplier display** |
| **C) Market Exchange** | NMG/NEOX swap widget, 1.5% fee indicator |
| **D) Onboarding** | "Welcome, Guild Master. You begin with 500 Gold and 3 free smelts..." |

See [game-ui-spec.md](./game-ui-spec.md) for full UI specification and [landing-page.md](./landing-page.md) for marketing copy.

---

## 8. Glossary

| Term | Definition |
|------|------------|
| **Emission Multiplier** | Dynamic scaling factor (1.0× → 0.75× → 0.50× → 0×) applied to smelting rewards based on Reserve depletion |
| **Tutorial Subsidy Pool** | 50,000 NMG sub-account funding 3 free Bronze catalyst burns per new player |
| **Smelting Reward Reserve** | 8,400,000 NMG pre-allocation paying all ingot redemption rewards — never minted |
| **Server-Enforced Escrow** | Miner rental and marketplace trades enforced by Smartnode consensus — not trustless smart contracts |
| **P_floor** | Industrial floor price (NEOX per NMG) derived from weighted smelting cost and 7-day moving average |
| **Gold** | In-game soft currency; F2P win layer; minted 1:250 from NMG deposit (one-way) |
| **Guild Miner** | In-game database asset (Biotech/Cyborg); not on-chain; not an NFT |
| **Obsidian Crust** | Hostile surface of Planetary Core 9-C where all mining operations occur |

---

## Footer

**Document Version:** 2.2.0  
**Author:** Lead Game Economist & Systems Architect

**Links:** [Home](#) · [Launch App](#) · [Download PDF](#) · [neoxa.exchange](https://neoxa.exchange)

---

### Disclaimer

This document describes the intended design of Terra-Forge: The Deep Core as of v2.2.0. Cryptocurrency and GameFi participation involve significant financial risk. NMG has no guaranteed value, peg, or fixed exchange rate. Past performance of similar projects does not predict future results. Smelting rewards depend on Reserve availability and emission scaling. Nothing in this document constitutes financial, legal, or investment advice. Participate only with funds you can afford to lose. This game does not use NFTs.

**End of Document — Terra-Forge: The Deep Core v2.2.0**
