# Prompt: Market External Link & Marketplace Deferral (MVP Scope)

Act as a Principal Web3 Frontend Engineer and Product Owner defining **MVP scope** for the Terra-Forge game portal (`web/game.html`).

**Important:** English only. No NFTs. Canonical: `.whitepaper` v2.2.1. Do not build in-game swap widgets or P2P marketplace for MVP.

---

## Product Decision

### Market (NMG ↔ NEOX) — External Only

**Do NOT** embed a swap widget, price chart, or slippage controls in the game portal for MVP.

Instead, the **Market** tab is a **redirect / CTA panel** that sends players to trade on the official exchange:

- Primary CTA button: **"Trade on neoxa.exchange →"**
- Secondary link: **"Create account / Register on neoxa.exchange"**
- URL: `https://neoxa.exchange` (or the live NMG/NEOX pair deep link when available)

**Copy requirements (English):**

> **NMG / NEOX Market**
>
> Terra-Forge does not host swaps inside the game. All NMG ↔ NEOX trading happens on **neoxa.exchange** — the official Neoxa DEX.
>
> To trade: connect your Neoxa wallet, log in or register on neoxa.exchange, and swap NMG for NEOX (or vice versa). A **1.5% DEX fee** goes to liquidity providers.
>
> NMG/NEOX trades at a **floating market price** — there is no fixed peg.

**Display on the panel (read-only, optional):**
- Spot price fetched from neoxa.exchange API (if available) — display only, no swap
- 24h change — display only
- Link text: "View live chart on neoxa.exchange →"

**Remove from MVP:**
- In-game swap input/output fields
- Slippage controls
- Embedded iframe widget
- "Phase 2 — Coming Soon" placeholder (replace with live external CTA)

---

### Marketplace (P2P Ore / Miner Rental) — Deferred

**Do NOT** ship P2P marketplace, ore listings, bids, or miner rental UI in MVP.

**Reason:** Server-enforced escrow, listing management, dispute resolution, and anti-abuse enforcement are too complex for the current launch scope.

**UI treatment:**

Option A (recommended): **Remove the Marketplace tab entirely** from the portal navigation.

Option B: Keep tab but show a permanent **"Not Available"** state:

> **Guild Marketplace — Not Available**
>
> P2P ore trading and miner rental require server-enforced escrow and are not available in this release.
>
> For now, progress using Gold, smelting, and direct gameplay. Marketplace may return in a future protocol phase subject to governance.

**Remove from MVP copy:**
- "Post ore listings, accept bids, rent out miners"
- "Phase 2 — Coming Soon" (misleading — this is deferred indefinitely, not Phase 2)

---

## Whitepaper & Docs Alignment

Update these references:

| Document | Change |
|----------|--------|
| `.whitepaper` §6 | Market = external CTA to neoxa.exchange; Marketplace = deferred |
| `.whitepaper` §4.6 | Mark P2P Ore Marketplace as **Phase 3 / Deferred** — design retained, not in MVP |
| `docs/game-ui-spec.md` | Section C = external link panel; Section D = removed or "Not Available" |
| `prompts/13-website-game-interface.md` | Same scope change |
| `prompts/04-wallet-exchange-interoperability.md` | Exchange integration = external link, not embed |
| Tutorial step 6 | Remove "sell ores P2P" as active feature; say "earn Gold through gameplay" |

**Win Matrix adjustment (F2P path for MVP):**

| Before (full spec) | MVP (no marketplace) |
|--------------------|------------------------|
| 500 Gold → mine → 3 subsidized Bronze → P2P ore sales | 500 Gold → mine → 3 subsidized Bronze → **Gold sinks (hire, repair, rest, upgrades)** |

P2P ore marketplace remains in the **long-term design** (§4.6) but is explicitly **out of MVP scope**.

---

## Visual Design (Market Tab)

- Industrial card layout matching existing portal style
- Large orange CTA button: "Trade on neoxa.exchange"
- Secondary ghost button: "Register / Log In"
- Small info row: "1.5% DEX fee · Floating price · No in-game peg"
- Optional: NEOX/USDC reference (0.00008 USDC) as footnote — ops-updated
- Icon: external-link arrow on all outbound buttons (`target="_blank" rel="noopener"`)

---

## Deliverables

1. Updated game portal UI spec (Market external CTA + Marketplace deferred).
2. Player-facing copy for both panels (English).
3. Whitepaper §6 MVP scope note.
4. Tutorial text revisions removing marketplace promises from onboarding.
5. Landing page FAQ: "Where do I trade NMG?" → neoxa.exchange.

No code in this prompt — specification and copy only.
