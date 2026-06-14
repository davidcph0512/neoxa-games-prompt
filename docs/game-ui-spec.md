# Terra-Forge: Game Portal UI Specification

**Version:** 2.2.0 | **Language:** English only | **No NFTs**

---

## Visual Design

**Style:** Industrial, Steampunk, gritty sci-fi. Dark mode default.

**Colors:** #1A1A24 (metallics) | #FF5500 (volcanic orange) | #0B0B0F (obsidian charcoal)

**UI patterns:** Glassmorphism cards, glowing orange active borders, smooth hover transitions, fully responsive (mobile/tablet/desktop).

---

## Sticky Header

- **Logo:** TERRA-FORGE: THE DEEP CORE
- **Wallet:** "Connect Wallet" or truncated address (e.g., G8Xp...3k91)
- **Balances:** NMG | Gold | Ores (aggregate count)
- **Emission indicator:** Small badge showing current multiplier (e.g., "1.0× Normal")

---

## Section A: Miner Command Center

**Purpose:** Manage all owned and rented miners.

**Per-miner card displays:**
- Miner ID (e.g., MINER_0982)
- Class badge: Biotech or Cyborg
- Rarity badge: Common | Rare | Epic | Legendary
- Durability bar (0–100)
- Fatigue bar (0.0–1.0)
- Current zone: Surface | Mid-Fracture | Deep Core
- Mining rate: Φ ores/hour

**Actions per miner:**
- "Send into Deep Crust" (dispatch)
- "Recall & Rest" (stop mining)
- "Repair" (10 Gold per 10 durability)
- "Camp Rest" (50 Gold, reset fatigue)

**Empty state:** "No miners deployed. Hire your first operative from the Guild Hall."

---

## Section B: Smeltery Forge

**Purpose:** Smelt ores into ingots and earn NMG from Reserve.

**Global display:**
- Current Emission Multiplier (large): e.g., "1.0× — Normal Operations"
- Reserve health bar (optional): percentage remaining

**Per-recipe card (Bronze, Iron, Mithril, Astral):**

| Field | Example (Bronze) |
|-------|------------------|
| Inputs | 100 Copper + 50 Coal |
| Your stock | 45/100 Copper, 30/50 Coal |
| Catalyst fee | 0.10 NMG (or "FREE — Tutorial Subsidy") |
| Base reward | 1.20 NMG |
| Effective reward | 1.20 NMG × multiplier |
| Net profit | +1.10 NMG |

**Forge Ingot button states:**
- **Active:** All materials + catalyst available
- **Disabled:** Missing materials (show what's needed in red)
- **Subsidized:** Bronze + tutorial charges remaining (show "2 free smelts left")

**Post-forge toast:** "Bronze Ingot forged. +1.20 NMG credited to your balance."

---

## Section C: Market Exchange

**Purpose:** NMG/NEOX swap via neoxa.exchange integration.

**Displays:**
- Spot price (NEOX per NMG)
- 24h change
- Slippage estimate
- **1.5% DEX fee** (prominent)
- Swap input/output fields
- Link: "Trade on neoxa.exchange →"

---

## Section D: P2P Guild Marketplace (Optional Tab)

- List ores for Gold or in-game NMG
- 2% trade fee indicator
- Escrow status with 1-hour timeout

---

## Onboarding Tutorial Modal

**Step 1 — Welcome**  
"Welcome, Guild Master. You begin with 500 Gold and 3 free Bronze smelts. Hire your first Miner and descend into the Obsidian Crust."

**Step 2 — Hire**  
"Hire a Common Biotech Miner for 200 Gold from the Guild Hall."

**Step 3 — Dispatch**  
"Send your miner into the Surface zone. Ores accumulate automatically."

**Step 4 — Collect & Forge**  
"When you have 100 Copper and 50 Coal, forge your first Bronze Ingot — free catalyst included."

**Step 5 — Optional Wallet**  
"Connect a wallet anytime to deposit NMG or withdraw earnings. Crypto is optional."

**Step 6 — Grow**  
"Sell ores, rent elite miners, or deposit NMG to accelerate. Everyone wins differently."

---

## Tooltips (English)

| Element | Tooltip |
|---------|---------|
| Gold | In-game currency. Pays for hire, rest, repairs. Cannot convert back to NMG. |
| NMG | On-chain token. Catalyst burns and withdrawal. Earned from smelting. |
| Fatigue | Increases 0.10/hour mining. At 1.0, mining stops until rest or cooling. |
| Emission Multiplier | Reward scaling based on Reserve health. Protects long-term sustainability. |
| Tutorial Subsidy | 3 free Bronze catalyst burns per account. Funded by community pool. |

---

## Responsive Notes

- **Mobile:** Stack miner cards vertically; collapse sidebar to hamburger
- **Tablet:** Two-column miner grid
- **Desktop:** Three-column grid with sticky header balances

---

## Copy Rules

- English only
- No NFT terminology
- Use "server-enforced rental" not "trustless"
- Show Effective Reward, not just Base Reward
- Always show emission multiplier when smelting
