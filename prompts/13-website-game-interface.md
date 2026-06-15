# Prompt: Game Portal & Dashboard Interface (Section 6)

Act as a Principal Web3 Frontend Engineer and Lead Game UI Designer. Your task is to design the complete, responsive **multi-page** in-game portal for **"Terra-Forge: The Deep Core"**.

**Important:** No NFTs exist in this game. All copy in English only. Canonical: `.whitepaper` v2.3.2. Show emission multiplier in Smeltery Forge.

**Critical implementation rules:**
1. **Every page MUST include images** — text-only UI is NOT acceptable. See § Image Assets.
2. **One primary function per page** — separate routes; never stack Command + Guild + Forge on one scroll.
3. **Low density, high breathing room** — if a viewport feels "busy", remove elements. See § Layout Density (mandatory).

---

## Layout Density & Breathing Room (Mandatory)

Web3 game portals should feel **cinematic and calm**, not like a crowded trading dashboard. Agents MUST follow these limits:

### Global density budget
- **Max 4 UI groups visible above the fold** on any page (e.g., hero + one card + one CTA — not hero + table + sidebar + 4 cards).
- **Section gap:** minimum **64px** between major sections; **48px** between cards in the same section.
- **Card padding:** minimum **24px** internal padding; **16px** gap between items inside a card.
- **Content width:** max **960px** centered (not 1200px) — narrower columns reduce crowding.
- **No data tables on main views** — use short stat rows or move details to a modal / "View details" expand.
- **Progressive disclosure:** show the minimum needed to act; hide secondary stats behind **"Details ▾"** or a second screen.

### Sticky header — keep it thin
The header must NOT become a second dashboard. **One row only** (64px height desktop):

| Left | Center | Right |
|------|--------|-------|
| Logo mark (icon only on mobile) | Nav links (5 max) | **Wallet chip** (single pill: `G8Xp…3k91 ▾`) |

**Balances (NMG, Gold, Ores) and emission multiplier live inside the Wallet chip dropdown** — NOT as separate inline chips in the header bar.

- Mobile: hamburger menu; logo + wallet chip only in the bar.
- Do NOT show address + 3 balance chips + emission badge + nav all in one crowded row.

### One focal action per view
Each page exposes **one primary CTA** above the fold. Secondary actions are text links or inside modals.

| Page | Primary CTA (only one prominent button above fold) |
|------|-----------------------------------------------------|
| Command Center | "Send to Surface" (on selected miner) OR "Recruit at Guild Hall →" (empty) |
| Guild Hall | "Rent — 50 Gold / 7 days" on Common (first tier only above fold) |
| Smeltery Forge | "Forge Ingot" on the **selected** recipe (one recipe focused at a time) |
| Market | "Trade on neoxa.exchange →" |

---

## Design Specifications

**Visual Style — Web3 Game Aesthetic:** Dark-mode sci-fi command deck. Industrial steampunk + Web3 game tropes.

- **Base palette:** #1A1A24, #0B0B0F, #FF5500
- **Web3 accents:** #00E5FF, #8B5CF6, #FFD700
- **Background:** subtle hex-grid + dark gradient — low contrast so foreground cards stand out
- **Cards:** glassmorphism, rarity borders, **large empty margins around each card**
- **Typography:** page title 32px; body 16px; line-height ≥ 1.6; never below 14px
- **Motion:** subtle hover scale only — no constant animations that add visual noise

**UI Architecture:** Multi-page routes + thin sticky header. Each page = hero + **one column** content.

**Language:** English only.

---

## Image Assets — Mandatory

Agents **must** include visible images on every screen. Use `/assets/images/`; if missing, styled placeholder frames with `alt` text — never omit the slot.

| Asset | Path | Size | Description |
|-------|------|------|-------------|
| Logo mark | `assets/images/logo-mark.png` | 64×64 | Forge anvil + chain link |
| Connect gate hero | `assets/images/wallet-gate-hero.jpg` | 1200×600 | Orbital forge hologram |
| Ore icons (×5) | `assets/images/ores/{name}.png` | 128×128 | Ore crystals |
| Ingot icons (×4) | `assets/images/ingots/{name}.png` | 128×128 | Forged bars |
| Zone panoramas (×3) | `assets/images/zones/{name}.jpg` | 800×400 | Cinematic zone art |
| Miner portraits (×8) | `assets/images/miners/{class}-{rarity}.png` | 512×512 | Character art |
| Empty state | `assets/images/empty-roster.png` | 400×300 | Empty command deck |

**Style:** gritty steampunk sci-fi, orange rim-light. Hero banners and portraits — not bare data tables.

---

## Multi-Page Information Architecture

| Route | Nav label | Purpose |
|-------|-----------|---------|
| `/command` | Command Center | Roster + dispatch only |
| `/guild-hall` | Guild Hall | Recruitment only |
| `/forge` | Smeltery Forge | Smelting only |
| `/market` | Market | External exchange CTA |
| `/zones` | Zone Atlas | Zone education (keeps Command Center clean) |

**Cross-page links:** empty roster → "Go to Guild Hall →"; after hire → "View in Command Center →".

**Do NOT** put Zone Intel sidebar on Command Center — link **"Open Zone Atlas →"** instead.

---

## Wallet Gate — Manual Sign-In

Full-screen gate until Neoxa sign-in per [dev.neoxa.net](https://dev.neoxa.net/).

**Layout (uncrowded):** hero image top 35% → **one step visible at a time** (stepper: Address → Sign → Verify). Do not show all 3 form blocks at once.

1. Headline + subcopy (2 lines max)
2. Step 1: address input + Next
3. Step 2: message to sign + Copy + accordion "How to sign" + Next
4. Step 3: signature paste + **Verify & Enter Forge**

Post-auth: 500 Gold + 3 Tutorial Subsidies.

---

## Page: Command Center (`/command`)

**Layout: single column. One miner card per row. No sidebar.**

```
[ Hero banner — full width, 240px tall ]

[ Miner card 1 — full width, portrait left / stats right ]
     OR
[ Empty state — centered image + one CTA ]

[ Text link: "Open Zone Atlas →" ]   ← not an inline comparison table
```

**Hero:** `heroes/command-center.jpg` + title + **one-line** subtitle.

**Miner card (ONE per row, full width, max 720px centered):**
- Portrait ~180px wide (left)
- Right column — **max 5 visible lines:**
  - Name + rarity badge
  - Durability bar | Fatigue bar (side by side)
  - Zone: 3 compact pills (Surface | Mid-Fracture | Deep Core) — one selected
  - Φ ores/hour (single number)
- **Primary action row (2 buttons max visible):** `Send to Surface` + `Recall & Rest`
- **Secondary actions** in **"More ▾"** menu: Repair, Camp Rest, View Details

**Do NOT show on the card:** full ore tables, lease legal text, upgrade info, shop buttons.

**Empty state:** centered `empty-roster.png` + "No operatives on roster" + single CTA **"Recruit at Guild Hall →"**

**Above-fold target:** hero + **one** miner card (or empty state) — nothing else.

---

## Page: Guild Hall (`/guild-hall`)

**Layout: vertical chapters. ONE miner tier fills the viewport per scroll stop.**

Each tier is a **full-width chapter** separated by 80px+ gap and a subtle divider line. Player scrolls through tiers like a character select screen — not a 4-column grid.

```
[ Hero — 240px ]

[ Intro — 2 sentences + wide interior image ]

--- scroll ---

[ Common Biotech chapter ]
  [ large portrait — centered, 280px ]
  [ 3 stat pills: Class | Rarity | Ideal zones ]
  [ 1 sentence rent vs buy explanation ]
  [ Rent button ]  [ Buy button — secondary/outline style ]

--- 80px gap ---

[ Rare Biotech chapter ]
  (same sparse pattern)

... Epic, Legendary ...
```

**Rules:**
- **One portrait centered** per tier — not portrait + stats + FAQ + table in one row
- **Two buttons max** per tier (Rent primary, Buy outline)
- Rent vs Buy comparison infographic: **one image at page bottom**, not inline with every card
- FAQ: **collapsed accordion at bottom only** (max 4 questions)
- No dispatch, no smelting, no roster list on this page

**Confirmation modal:** portrait + 3 bullet terms + single **Confirm Lease** button. No walls of text.

---

## Page: Smeltery Forge (`/forge`)

**Layout: recipe selector tabs + ONE expanded recipe card.**

Do NOT show all 4 recipes fully expanded in a 2×2 grid.

```
[ Hero — 240px ]

[ Emission badge — single pill centered: "1.0× Normal Operations" ]

[ Tab strip: Bronze | Iron | Mithril | Astral ]

[ Selected recipe card — full width, max 640px centered ]
  [ Ingot icon 128px — centered ]
  [ Inputs: 3 ore icons + counts — one row ]
  [ 3 stat lines: Catalyst | Reward | Net ]
  [ Forge Ingot — single primary button ]
```

Switching tabs swaps the one card. Other recipes are **not visible** until selected.

**Reserve health bar:** optional, below emission badge — thin single line, not a large widget.

---

## Page: Market (`/market`)

**Layout: hero + one CTA block + one diagram. Nothing else above fold.**

```
[ Hero — 240px ]

[ Card — max 480px centered ]
  [ flow diagram image ]
  [ "Trade on neoxa.exchange →" — primary ]
  [ "Register / Log In" — text link below ]
  [ 1.5% fee — footnote, 12px muted ]
```

Optional spot price: **one line** under the CTA, not a ticker + chart + table.

---

## Page: Zone Atlas (`/zones`)

**Layout: one zone card per viewport section (same chapter pattern as Guild Hall).**

Each zone = full-width panorama image (min 360px tall) + **4 lines of text** + text link "Dispatch from Command Center →".

No comparison table on this page — the scroll itself compares zones visually.

---

## Onboarding — Spotlight (Cross-Page)

Dim overlay + one spotlight target per step. Tutorial navigates between pages.

| Step | Page | Spotlight |
|------|------|-----------|
| 1 | Any | Nav **Guild Hall** |
| 2 | `/guild-hall` | Common **Rent** button |
| 3 | `/guild-hall` | **Confirm Lease** |
| 4 | `/command` | Surface zone pill |
| 5 | `/command` | **Send to Surface** |
| 6 | `/forge` | **Forge Ingot** |
| 7 | `/zones` | Mid-Fracture section |
| 8 | Any | Wallet chip → deposit |

---

## Anti-Patterns — Do NOT Build

- ❌ Crowded header with address + 3 balances + emission + 5 nav items inline
- ❌ Multi-column dashboard grids (2×2 recipes, 3-column miner grids)
- ❌ Sidebars on Command Center (move zone info to `/zones`)
- ❌ All form fields visible at once on wallet gate
- ❌ Tables, tickers, and FAQ on the same viewport as primary action
- ❌ More than 2 buttons visible per card without a "More" menu
- ❌ Single-page layout stacking all game functions
- ❌ Text-only UI without images

---

## Deliverables

Per-page spec in English with:
- Image asset list (paths, dimensions, descriptions)
- **Density audit:** list what is hidden vs visible above the fold for each page
- Multi-page routing, thin header, single-column layouts
- Guild Hall as sparse character-select chapters
- Command Center as one-card-per-row roster
- Forge as tabbed single-recipe view
- Cross-page tutorial spotlights

The portal must feel **spacious, focused, and cinematic** — like a Web3 game, not a cramped admin panel. No NFTs. English only.
