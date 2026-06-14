# Prompt: Game Portal & Dashboard Interface (Section 6)

Act as a Principal Web3 Frontend Engineer and Lead Game UI Designer. Your task is to design the complete, responsive in-game portal and dashboard for **"Terra-Forge: The Deep Core"**.

**Important:** No NFTs exist in this game. All copy in English only. Canonical: `.whitepaper` v2.3.0. Show emission multiplier in Smeltery Forge.

---

## Design Specifications

**Visual Style — Web3 Game Aesthetic:** Dark-mode sci-fi command deck that reads as a **blockchain-native game**, not a corporate dashboard. Layer industrial steampunk lore with Web3 game UI tropes:

- **Base palette:** deep metallics (#1A1A24), obsidian charcoal (#0B0B0F), volcanic orange (#FF5500)
- **Web3 accents:** electric cyan (#00E5FF), neon violet (#8B5CF6), chain-gold highlights (#FFD700) for on-chain actions
- **Patterns:** hex-grid backgrounds, subtle scanline overlay, animated particle embers, pulsing glow on active chain actions
- **Cards:** glassmorphism + rarity-colored borders (Common grey → Legendary gold shimmer); RPG stat panels with icon + value rows
- **Typography:** bold condensed headers for zone/miner names; monospace for addresses, signatures, and ore counts
- **Motion:** smooth scale-on-hover, loot-pop micro-animations on ore credit, shimmer on "Connect Wallet" CTA
- **Chain affordances:** Neoxa chain badge on wallet chip, "On-Chain" pill on burn/deposit/withdraw buttons

**UI Architecture:** Fully responsive (mobile / tablet / desktop). Sticky header. Tab or sidebar nav between portal zones (sections A–D below).

**Language:** English only for all player-facing text, tooltips, buttons, error messages, and onboarding content.

---

## Wallet Gate — Required Before Play (MVP: Manual Sign-In)

**No browser wallet extension is available at launch.** The portal is **blocked** until the player authenticates with a Neoxa address and a signed message. Follow [Neoxa Developer Docs](https://dev.neoxa.net/) identity verification (`signmessage` + `POST /agents/verify-message`).

### Connect Wallet Modal (full-screen gate on first visit)
1. **Headline:** "Connect Your Neoxa Wallet"
2. **Subcopy:** "Sign in with your Neoxa address to enter the forge. Browser extension coming soon — use manual sign-in for now."
3. **Step 1 — Address:** text input, `G…` prefix validation via `isValidAddress`
4. **Step 2 — Sign message:** display server-issued nonce message exactly, e.g. `terra-forge-login:{nonce}`
   - **"Copy Message"** button
   - Collapsible **"How to sign"** accordion linking to https://dev.neoxa.net/ (SDK `signMessage`, Neoxa Core GUI, or `@neoxa/game-sdk` CLI)
5. **Step 3 — Paste signature:** text input for base64 signature returned by the wallet
6. **Primary CTA:** "Verify & Enter Forge"
7. **On success:** truncated address in header (e.g., `G8Xp…3k91`), session cookie/JWT, portal unlocks
8. **On failure:** inline error — `INVALID_ADDRESS`, `bad_signature`, etc.
9. **Future slot:** disabled **"Neoxa Wallet Extension"** button with "Coming Soon" badge (do not implement extension yet)

**Post-auth:** new accounts still receive 500 Starter Gold + 3 Tutorial Catalyst Subsidies (§3.1). Wallet auth gates **access**, not crypto deposit.

---

## Portal Layout — Section Map

| Section | Name | Purpose |
|---------|------|---------|
| **A** | Miner Command Center | Roster, zone dispatch, fatigue/durability |
| **B** | Smeltery Forge | Ingot recipes, catalyst burns, NMG rewards |
| **C** | Market | External CTA to neoxa.exchange (no in-game swap) |
| **D** | Guild Hall Shop | Rent vs Buy miners (no P2P) |

---

## Mining Zones — UI Specification (Section A)

Each miner card includes a **zone selector** (dropdown or three-tab strip). A persistent **"Zone Intel"** comparison panel (sidebar on desktop, bottom sheet on mobile) explains the three zones at a glance:

| Zone | Speed (γ_depth) | Ore Profile | Best For | Access |
|------|-----------------|-------------|----------|--------|
| **Surface** | 1.0× | 45% Copper, 30% Iron, 25% Coal — **no** Mithril or Star-Element | Bronze smelting, F2P starter loop | All miners, default for new accounts |
| **Mid-Fracture** | 1.3× | 30% Copper, 25% Iron, 25% Coal, **15% Mithril**, **5% Star-Element** | Iron ingots, first rare ore exposure | Unlocked after first Bronze Ingot forged |
| **Deep Core** | 1.6× | 15% Copper, 20% Iron, 25% Coal, **30% Mithril**, **10% Star-Element** | Mithril & Astral ingots | Unlocked when roster holds Epic or Legendary Cyborg |

**Per-zone UI elements:**
- Zone icon + color tint: Surface (amber), Mid-Fracture (orange-red), Deep Core (crimson + radiation pulse)
- Live **Φ ores/hour** recalculates when zone changes
- Mini ore-distribution bar chart on each zone tab
- **Locked zones:** greyed tab + padlock + unlock requirement tooltip
- Dispatch CTA label adapts: **"Send to Surface"** / **"Send to Mid-Fracture"** / **"Send to Deep Core"**
- Active mining badge shows current zone name + glow matching zone color

---

## Core Dashboard Sections

### Sticky Header
- Brand logo: "TERRA-FORGE: THE DEEP CORE"
- Neoxa chain badge + truncated address when connected; **"Connect Wallet"** reopens manual sign-in if session expires
- Balance chips: NMG (on-chain pill) | Gold | Ores (aggregate)
- Emission multiplier badge (e.g., "1.0× Normal")

### Section A: Miner Command Center
- All **owned** and **leased** miners as RPG-style cards:
  - Miner ID, Class (Biotech / Cyborg), Rarity badge with color border
  - Durability bar, Fatigue bar (0.0–1.0)
  - Zone selector + current Φ ores/hour
- Actions: zone-aware dispatch, "Recall & Rest", "Repair", "Camp Rest"
- Empty state: "No miners deployed. Visit the Guild Hall to hire your first operative."

### Section B: The Smeltery Forge
- Large emission multiplier display + Reserve health (optional)
- Four ingot recipe cards: Bronze, Iron, Mithril, Astral
- Per-recipe: inputs, stock, catalyst fee, base/effective reward, net profit
- **"Forge Ingot"** button — active / disabled / subsidized states
- Post-forge toast with loot-pop animation

### Section C: Market (External CTA — MVP)
- **No in-game swap widget.** Direct players to neoxa.exchange.
- Primary: "Trade on neoxa.exchange →" (new tab)
- Secondary: "Register / Log In on neoxa.exchange"
- Optional read-only spot price + 24h change; 1.5% DEX fee footnote
- Copy: floating NMG/NEOX price — no peg

### Section D: Guild Hall Shop — Rent vs Buy (No P2P)
- Each miner card: **[ Rent — X / 7 days ]** and **[ Buy — Y forever ]**
- Leased: "LEASED — 5d 12h remaining" | Owned: "OWNED"
- No P2P ore marketplace. See `20-guild-shop-rent-vs-buy-no-p2p.md`

### Marketplace tab — Removed
- Do NOT include a Marketplace tab. P2P removed in v2.3.0.

---

## Onboarding / Tutorial — Spotlight System

Interactive guided tour **after** wallet sign-in. Each step **dims the full UI** (80% dark overlay) and **spotlights** exactly one target element with a pulsing orange ring + arrow tooltip.

| Step | Message (summary) | Spotlight target |
|------|-------------------|------------------|
| 1 | Welcome — 500 Gold + 3 free Bronze smelts | Guild Hall nav tab |
| 2 | Hire your first miner | **Common Biotech `[ Rent — 50 Gold / 7 days ]` button** (primary F2P path) |
| 3 | Confirm rent | Rent confirmation modal **"Confirm Lease"** button |
| 4 | Choose mining zone | Surface zone tab on miner card |
| 5 | Dispatch | **"Send to Surface"** button on miner card |
| 6 | Collect & forge | **"Forge Ingot"** on Bronze recipe (when materials ready) |
| 7 | Go deeper (later) | Zone Intel panel — Mid-Fracture unlock hint |
| 8 | Optional NMG | Header NMG chip → deposit flow (1 NMG = 250 Gold) |

**Spotlight rules:**
- Only the highlighted element receives pointer events; rest of UI is inert
- **"Next"** disabled until the player clicks the spotlighted control (or completes the action)
- **"Skip Tour"** in tooltip corner — persists `tutorial_completed` flag
- Step 2 **must** spotlight the **Rent** button, not Buy — F2P path is rent-first (50 Gold vs 200 Gold buy)
- Tooltip copy example for Step 2: *"Rent a Common Biotech for 50 Gold / 7 days. Tap the highlighted Rent button to begin."*

---

## Deliverables

A complete visual and UX design specification in English for every dashboard section, including: wallet gate flow, zone comparison UI, component descriptions, spotlight tutorial mechanics, user flows, interaction states, responsive behavior, and all player-facing copy. The design must feel like a **Web3-native game command deck** — immersive, chain-aware, and production-ready. No NFTs. English only.
