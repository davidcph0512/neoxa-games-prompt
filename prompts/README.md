# Terra-Forge: The Deep Core — Prompt Index

English prompts for Terra-Forge v**2.2.0**. Canonical source: **`.whitepaper`**

**Global rules:**
- English only
- No NFTs — Guild Miners are in-game database assets
- NMG/NEOX is a floating market pair — not pegged
- Everyone winnable — each player class has a designed non-zero path
- All numeric values: **`16-economy-numbers-bible.md`**

## Prompt Files

| File | Section | Focus |
|------|---------|-------|
| [00-executive-summary.md](./00-executive-summary.md) | Executive Summary | GameFi 2.0 vision, everyone winnable |
| [01-worldview-abyssal-descent.md](./01-worldview-abyssal-descent.md) | §1.1 | Lore, Planetary Core 9-C |
| [02-worldview-mining-guilds.md](./02-worldview-mining-guilds.md) | §1.2 | Guild Master, miners, foundry |
| [03-dual-token-asset-taxonomy.md](./03-dual-token-asset-taxonomy.md) | §2.1 | Assets, Reserve accounting |
| [04-wallet-exchange-interoperability.md](./04-wallet-exchange-interoperability.md) | §2.2 | Wallet, deposit, withdraw |
| [05-mining-speed-equation.md](./05-mining-speed-equation.md) | §3.1 | Mining formula, ore drops, durability |
| [06-forging-smelting-recipes.md](./06-forging-smelting-recipes.md) | §3.2 | Smelting, subsidies, emission scaling |
| [07-revenue-share-active-players.md](./07-revenue-share-active-players.md) | §4.1 | F2P loop, Gold win layer |
| [08-revenue-share-capital-providers.md](./08-revenue-share-capital-providers.md) | §4.2 | Elite miners, server-enforced rental |
| [09-revenue-share-liquidity-providers.md](./09-revenue-share-liquidity-providers.md) | §4.3 | DEX, 1.5% fee |
| [10-revenue-share-smartnode-operators.md](./10-revenue-share-smartnode-operators.md) | §4.4 | Smartnodes, anti-cheat authority |
| [11-upgrade-cost-function.md](./11-upgrade-cost-function.md) | §5.1 | Upgrades, 80/20 burn split |
| [12-automated-floor-buybacks.md](./12-automated-floor-buybacks.md) | §5.2 | Buyback formula, guardrails |
| [13-website-game-interface.md](./13-website-game-interface.md) | §6 | In-game dashboard UI |
| [14-landing-page.md](./14-landing-page.md) | — | Marketing landing page (v2.2 messaging) |
| [15-whitepaper-web-page.md](./15-whitepaper-web-page.md) | Full doc | Online whitepaper page v2.2.0 |
| [16-economy-numbers-bible.md](./16-economy-numbers-bible.md) | **Canonical** | All numeric values |
| **[17-sustainability-everyone-wins.md](./17-sustainability-everyone-wins.md)** | **§4.7 + §5.5–5.6** | **Sustainability & win matrix docs** |
| **[18-game-prototype-economy-calibration.md](./18-game-prototype-economy-calibration.md)** | **§6.1** | **Fix prototype NMG inflation (mining + recipe audit)** |
| **[20-guild-shop-rent-vs-buy-no-p2p.md](./20-guild-shop-rent-vs-buy-no-p2p.md)** | **§3.6 + §4.5** | **Guild Shop rent/buy; P2P permanently removed** |

## Recommended Generation Order

```
1. 16-economy-numbers-bible     (numbers first)
2. 17-sustainability-everyone-wins (sustainability narrative)
3. .whitepaper / 15             (full spec web page)
4. 00–12                        (section prompts)
5. 14                           (landing page)
6. 13                           (game UI)
```

## v2.3.1 Changelog (UI & wallet gate)

- **Web3 game aesthetic:** hex grids, chain badges, rarity borders, loot-pop animations
- **Wallet gate required:** manual Neoxa address + signmessage per https://dev.neoxa.net/ (extension deferred)
- **Mining zone UI spec:** Surface / Mid-Fracture / Deep Core comparison panel + unlock rules
- **Tutorial spotlight:** dim overlay + pulse ring on target control (Rent button on step 2)
- **Guild Hall as Section D** in portal layout

## v2.3.0 Changelog (from v2.2.1)

- **No P2P:** Ore marketplace and player-to-player miner rental permanently removed
- **Guild Shop rent vs buy:** Rent at 25% of buy price for 7 days; buy = permanent
- **Capital Provider → Industrial Investor:** Buy own miners, smelt for NMG (no landlord role)
- New prompt: `20-guild-shop-rent-vs-buy-no-p2p.md`

## v2.2.1 Changelog (from v2.2.0)

- **Market MVP scope:** External CTA to neoxa.exchange only — no in-game swap widget
- **Marketplace deferred:** P2P ore/miner rental not in MVP; §4.6 design retained for future
- **Prototype calibration:** New prompt `18` — fix mining rate (ores/hr) and recipe inputs
- **§6.1 Implementation notes:** Document common prototype errors that inflate NMG

## v2.2.0 Changelog (from v2.1.0)

- **Tutorial Catalyst Subsidy:** 3 free Bronze smelts per account (Tutorial Pool 50,000 NMG)
- **Dynamic Emission Scaling:** 1.0× → 0.75× → 0.50× → pause as Reserve depletes
- **Catalyst Recycle:** 5% → Reserve, 95% burned on-chain
- **§4.7 Win Matrix:** Explicit non-zero path for every player class
- **Gold as F2P win layer:** NMG is withdrawal layer, not only win condition
- **§5.5 Sustainability Guardrails:** smelt cap, withdraw cooldown, Reserve alert
- **§5.6 Reserve Runway Model:** ~6.4 years Bronze example, honest multi-year sustainability
- New prompt: `17-sustainability-everyone-wins.md`

## v2.1.0 Changelog (from v2.0.4)

- Removed NFTs; English only; 21M allocation; NMG→Gold 1:250; fixed buyback math; server-enforced rental; NEOX/USDC reference
