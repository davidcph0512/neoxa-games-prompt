# Prompt: Game Portal & Dashboard Interface (Section 6)

Act as a Principal Web3 Frontend Engineer and Lead Game UI Designer. Your task is to design the complete, responsive in-game portal and dashboard for **"Terra-Forge: The Deep Core"**.

**Important:** No NFTs exist in this game. All copy in English only. Canonical: `.whitepaper` v2.2.0. Show emission multiplier in Smeltery Forge.

---

## Design Specifications

**Visual Style:** Industrial, Steampunk, gritty sci-fi. Dark mode by default. Primary colors: deep metallics (#1A1A24), glowing volcanic orange (#FF5500), and obsidian charcoal (#0B0B0F).

**UI Architecture:** Glassmorphism for dashboard cards, glowing orange borders for active statuses, smooth scaling hover transitions, and fully responsive layouts for mobile, tablet, and desktop.

**Language:** English only for all player-facing text, tooltips, buttons, error messages, and onboarding content.

---

## Core Dashboard Sections

### Sticky Header
- Custom brand logo: "TERRA-FORGE: THE DEEP CORE"
- Wallet status indicator showing "Connect Wallet" when disconnected, or a truncated address (e.g., G8Xp...3k91) when connected
- Active balance display for NMG, Gold, and raw Ores

### Section A: Miner Command Center
- Display all owned and rented miners with individual cards showing:
  - Miner ID (e.g., MINER_0982)
  - Miner Class (Biotech or Cyborg)
  - Rarity Badge (Common, Rare, Epic, Legendary)
  - Durability progress bar
  - Fatigue progress bar (0.0 to 1.0 scale)
- Action buttons per miner: "Send into Deep Crust" and "Recall & Rest"

### Section B: The Smeltery Forge
- Display all four premium ingot recipes: Bronze, Iron, Mithril, and Astral
- Per-recipe display showing raw ore requirements, NMG catalyst fees, expected NMG reward, and net profit
- "Forge Ingot" button with active and disabled states based on available materials and NMG balance

### Section C: Market (External CTA — MVP)
- **No in-game swap widget.** Direct players to neoxa.exchange.
- Primary button: "Trade on neoxa.exchange →" (external link, new tab)
- Secondary button: "Register / Log In on neoxa.exchange"
- Optional read-only spot price and 24h change (from exchange API)
- Prominent 1.5% DEX fee footnote
- Copy: floating NMG/NEOX price — no peg

### Marketplace — NOT in MVP
- Do NOT build P2P ore listings, bids, or miner rental UI for launch.
- Remove Marketplace tab OR show permanent "Not Available" state.
- See `19-market-external-marketplace-deferred.md` for full scope.

### Onboarding / Tutorial Modal
- Interactive greeting for new players with the message:
  "Welcome, Guild Master. You begin with 500 Gold and 3 free Bronze smelts. Hire your first Miner and descend into the Obsidian Crust."
- Step-by-step guided tour covering: Starter Gold, hire miner (200 Gold), dispatch, collect ores, forge bronze, optional wallet connect and NMG deposit (1 NMG = 250 Gold)

---

## Deliverables

A complete visual and UX design specification in English for every dashboard section, including component descriptions, user flows, interaction states, responsive behavior, and all player-facing copy. The design must feel industrial, immersive, and production-ready. No NFTs. English only.
