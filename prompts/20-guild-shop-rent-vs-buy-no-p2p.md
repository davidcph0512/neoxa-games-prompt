# Prompt: Guild Shop Rent vs Buy — No P2P (v2.3.0)

Act as a Lead Game Economist and Product Designer for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. No P2P. Canonical: `.whitepaper` v2.3.0 and `16-economy-numbers-bible.md`.

---

## Design Decision

**Remove all player-to-player systems:**
- No P2P ore marketplace
- No P2P miner rental / escrow / ore splits between players
- No player listings, bids, or marketplace fees

**Replace with Guild Shop dual mode:**
Every miner tier offers two options from the **same Guild Hall shop**:

| Mode | Cost | Duration | Ownership |
|------|------|----------|-----------|
| **Rent** | 25% of buy price | **7 days** | Temporary — miner removed at expiry |
| **Buy** | Full price | **Permanent** | Forever — miner stays in roster |

---

## Canonical Pricing

### Buy (Permanent) — unchanged from v2.2

| Rarity | Class | Buy Cost |
|--------|-------|----------|
| Common | Biotech | 200 Gold |
| Rare | Biotech | 800 Gold |
| Epic | Cyborg | 50 NMG |
| Legendary | Cyborg | 200 NMG (500/epoch) |

### Rent (7-Day Lease) — 25% of buy price

| Rarity | Class | Rent Cost (7 days) |
|--------|-------|-------------------|
| Common | Biotech | 50 Gold |
| Rare | Biotech | 200 Gold |
| Epic | Cyborg | 15 NMG |
| Legendary | Cyborg | 60 NMG |

**Rent rules:**
- Lease timer starts on hire confirmation
- Rented miner removed from roster at expiry (ores already mined stay with player)
- Rented miners **cannot be upgraded** (L_tool locked at 1)
- Player pays repair/rest costs during lease (Gold sinks)
- Max **2 active rented miners** per account (anti-abuse)
- No refund on early return
- Buy option always available — rent is a trial path, not a trap

**Buy rules:**
- Permanent roster slot
- Eligible for drill upgrade (L1→L2: 1.50 NMG + 25 Gold)
- Repair/rest as normal

---

## Why No P2P

| P2P problem | Guild Shop solution |
|-------------|---------------------|
| Escrow complexity | Server owns all miners; simple lease timer |
| Disputes / scams | No player counterparty |
| Marketplace moderation | No listings to police |
| Capital Provider passive rental | Investors **buy** miners and **smelt** for NMG directly |
| F2P ore sales for Gold | Gold sinks: rent, buy, repair, rest, upgrades |

---

## Updated Win Matrix (No P2P)

| Player Class | Primary Win | Path |
|--------------|-------------|------|
| Active F2P | Gold + ~3.6 tutorial NMG | 500 Gold → rent Common (50G/7d) or buy (200G) → mine → smelt |
| Active invested | Smelting NMG + withdraw | Deposit NMG → buy Epic/Legendary → deeper zones → higher ingots |
| Industrial investor | Smelting net NMG (passive) | Buy Legendary → dispatch Deep Core → smelt Astral/Mithril |
| Liquidity Provider | 1.5% DEX fees | neoxa.exchange — unchanged |
| Smartnode Operator | 45% block rewards | Unchanged |

**Removed:** Capital Provider as P2P landlord. Renamed to **Industrial Investor** — buys own miners, smelts own ore.

---

## Guild Shop UI — Dedicated Guild Hall Page (`/guild-hall`)

**Do NOT place recruitment on the Command Center page.** Guild Shop lives on its own route with hero art, lore, and large miner portraits. See `13-website-game-interface.md`.

Each miner **showcase card** (one tier per section, spaced vertically):

```
[ biotech-common.png — large portrait ]

Common Biotech
  Class: Biotech | Rarity: Common
  Ideal zones: Surface, Mid-Fracture
  "Rent 50 Gold for 7 days to trial. Buy 200 Gold for permanent roster."

  [ Rent — 50 Gold / 7 days ]   [ Buy — 200 Gold forever ]
```

Rented miners show badge on **Command Center** only: **"LEASED — 5d 12h remaining"**
Owned miners show badge: **"OWNED"**

**Required images per tier:** miner portrait PNG (512×512), wing banner, Guild Hall hero.

**Tutorial integration:** Steps 1–3 happen on `/guild-hall`. Step 2 spotlight = **Rent** button on Common Biotech. See `13-website-game-interface.md`.


---

## Deliverables

1. Updated §3.6 Guild Shop spec (rent vs buy tables and rules).
2. Revised §4 revenue share (remove §4.5 P2P rental, §4.6 P2P marketplace).
3. Updated Win Matrix and F2P path (no ore sales).
4. Game UI shop spec: dual-button layout, lease timer display.
5. FAQ: "Can I trade ores with other players?" → No. Ores are for smelting only.

All numbers must match `16-economy-numbers-bible.md` §8. No code.
