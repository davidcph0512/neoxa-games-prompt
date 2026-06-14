# Prompt: Dual-Token Microeconomics — Asset Taxonomy (Section 2.1)

Act as a Blockchain Systems Architect and Game Economist documenting the complete asset taxonomy for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. All gameplay assets except NMG are in-game database records. Canonical numbers: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`.

## Economic Architecture

Terra-Forge separates on-chain NMG from in-game industrial assets. NMG/NEOX trades at a **floating market price** on neoxa.exchange — not a peg.

**Flow:**
- neoxa.exchange (NMG/NEOX, floating)
- NMG → Gold (1 NMG = 250 Gold, one-way irreversible deposit)
- Gold → hire miners, pay rest, repairs, upgrades
- Guild Miners → extract ores → forge ingots
- Catalyst burn (on-chain: 95% burned, 5% recycled to Reserve) → scaled NMG reward from **Smelting Reward Reserve** (8.4M — never minted)
- Tutorial Subsidy Pool (50,000 NMG cap) funds first 3 Bronze catalyst burns per account

## Asset Specifications

### NMG — Miner Guild Token
- Neoxa L1 native asset, hard cap 21,000,000
- Supply allocations: see Economy Numbers Bible §2
- On-chain actions: deposit, burn, withdrawal
- Smelting rewards debit Reward Reserve — NOT new mint

### Gold — In-Game Soft Currency
- Database only; minted at 1 NMG = 250 Gold on deposit
- One-way only; shields players from market volatility
- New accounts receive 500 Starter Gold (one-time)
- F2P win layer: leaderboard, guild rank, marketplace wealth

### MINER — Guild Miners
- Database only — NOT on-chain, NOT NFTs
- Biotech / Cyborg; rarity Common → Legendary
- Tradable and rentable via in-game marketplace (server-enforced escrow)

### Ores — Raw Materials
- Database only: Copper, Iron, Coal, Mithril, Star-Element
- Drop rates vary by mining zone — see Economy Numbers Bible §6

### Ingots — Refined Products
- Bronze, Iron, Mithril, Astral
- Redemption keys for scaled NMG from Reward Reserve (Effective_Reward = Base × Emission_Multiplier)

## Your Task

Write a complete asset taxonomy document in English covering lifecycle, conversion rules, on-chain vs off-chain boundaries, and how the 21M cap is preserved through Reserve accounting.

## Key Rules

- No NFTs. No on-chain miners.
- Gold → NMG forbidden.
- Smelting never mints NMG.
- All NMG burns confirmed on-chain.
