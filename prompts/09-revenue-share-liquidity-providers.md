# Prompt: GameFi 2.0 Revenue Share — Liquidity Providers & Traders (Section 4.3)

Act as a DeFi Product Designer documenting the Liquidity Provider and Trader economy for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. NMG/NEOX is a **floating market price** — not pegged. NEOX reference: 0.00008 USDC. Canonical: `.whitepaper` v2.2.0.

## Player Profile

**Liquidity Providers and Traders — Market makers who supply capital to trading pools, independent of game mechanics.**

## Platform

- Exchange: Neoxa Exchange (neoxa.exchange)
- Primary trading pair: NMG / NEOX
- DEX swap fee: 1.5% per swap, distributed proportionally to Liquidity Provider pool share

## Core Value Proposition

- Supply NMG and NEOX to trading pools for deep, low-slippage order books.
- Earn 1.5% swap fees on every trade proportional to LP share.
- Self-sustaining financial market completely independent of speculative game mechanics.
- Traders profit from NMG price movements without ever playing the game.

## Economic Flow

Liquidity Providers stake NMG/NEOX into pools on neoxa.exchange. Traders and players swap NMG for NEOX (and vice versa). Every swap collects a 1.5% fee distributed to LPs. Game smelting profits create natural buy pressure on NMG, while LP depth ensures players can exit positions with minimal slippage.

## Your Task

Write a complete Liquidity Provider and Trader design document covering:

1. **Exchange integration:** How the game portal connects to neoxa.exchange for NMG/NEOX swaps, price display, and charts.
2. **Swap widget requirements:** Input/output amounts, slippage estimate, price impact, and prominent 1.5% fee indicator on every swap preview.
3. **LP dashboard:** Pool position display (NMG staked, NEOX staked, pool share percentage), accumulated fees earned, and estimated APY based on recent volume.
4. **Price feed usage:** How spot price data supports in-game displays, treasury buyback calculations, and marketplace price suggestions.
5. **Trader tools:** Price alerts, trade history, and limit order support where the exchange API allows.
6. **Economic independence:** Why LP rewards come entirely from DEX fees — not from game treasury or token inflation — and how this creates a financial layer separate from gameplay.

## Design Goal

The DEX layer must function as a self-sustaining financial market that benefits Liquidity Providers and Traders regardless of game activity, while game activity naturally drives NMG demand that benefits the entire ecosystem.
