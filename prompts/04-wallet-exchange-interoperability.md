# Prompt: Wallet & Exchange Interoperability (Section 2.2)

Act as a Web3 Product Designer and Integration Specialist documenting wallet and exchange connectivity for **Terra-Forge: The Deep Core**.

**Important:** English only. Wallet integration covers NMG only. Guild Miners are in-game assets. No NFTs. Canonical numbers: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`.

## Supported Wallets

Players connect any standard L1 non-custodial wallet to start playing, including:
- Bitget Wallet
- Atomic Wallet
- Neoxa Core GUI Wallet
- Any wallet supporting Neoxa L1 native assets

## On-Chain Specifications

- Network: Neoxa Layer-1
- Block confirmation time: approximately 60 seconds
- Network fees: minimal
- Primary on-chain asset: NMG (native L1 token)
- No on-chain miner assets — all miners exist in the game database

## External Exchange

- Platform: Neoxa Exchange (neoxa.exchange)
- Primary trading pair: NMG / NEOX
- Players export earned NMG to their wallets and swap freely for NEOX or other liquid crypto assets

## Your Task

Write a complete wallet and exchange interoperability specification covering every player-facing flow. All copy and documentation must be written in English only.

## Flows to Document

### Wallet Connection (Required Gate — MVP Manual Sign-In)

**Browser wallet extension is NOT available at launch.** Players must authenticate before accessing the portal. Implementation follows [Neoxa Developer Docs](https://dev.neoxa.net/) identity verification.

**Flow:**
1. Portal loads → full-screen **Connect Wallet** modal blocks all content
2. Server generates session nonce; client displays sign message: `terra-forge-login:{nonce}`
3. Player enters Neoxa address (`G…` prefix) and pastes signature from their wallet
4. Backend verifies via `POST https://assets.neoxa.net/agents/verify-message` with `{ address, signature, message }`
5. On `valid: true` → create session, unlock portal, show truncated address in header
6. On failure → inline error; do not grant access

**How to sign (player-facing help):**
- Link to https://dev.neoxa.net/ for SDK `signMessage`, Neoxa Core GUI, or `@neoxa/game-sdk`
- Provide **Copy Message** button for the exact nonce string
- Collapsible accordion: step-by-step sign instructions per wallet type

**Future:** placeholder **"Neoxa Wallet Extension — Coming Soon"** button (disabled); when extension ships, replace manual paste with one-click connect using the same verify-message backend.

**Disconnect:** clear session; return to Connect Wallet gate.

**Post-auth balances:** show on-chain NMG balance in header (via Asset API `GET /addresses/{address}/assets`) plus in-game Gold and ores.

### NMG Deposit (Irreversible — Start Playing)
- Player sends NMG from wallet to game treasury address on L1
- System waits for block confirmation (~60 seconds)
- Upon confirmation, Gold is minted at **1 NMG = 250 Gold** (irreversible)
- Display transaction confirmation and updated balances
- Clearly communicate that this conversion cannot be reversed

### NMG Withdrawal / Ingot Redemption
- Player earns NMG through smelting (paid from Smelting Reward Reserve — scaled by emission multiplier)
- Min withdrawal: 1 NMG; daily cap: 100 NMG per account
- **24-hour cooldown** before first withdrawal on new accounts (Sybil protection)
- System validates balance and transfers from Reward Reserve wallet on L1

### Tutorial Catalyst Subsidy (No NMG Deposit Required)
- Wallet **sign-in** is required to access the portal; **NMG deposit is not** required to start
- First 3 Bronze smelts: catalyst burned from Tutorial Subsidy Pool; player pays 0 NMG
- After subsidies exhausted, player wallet or in-game NMG balance required for catalyst

### NMG Burn Operations
- Forging catalyst fees (95% burned, 5% recycled to Reserve) and upgrade burns (80% burned)
- Player wallet signs burn transaction to on-chain burn address
- In-game state updates only after burn confirmation

### Exchange Integration (MVP — External Only)
- **Do NOT embed** a swap widget or iframe in the game portal for MVP.
- Market tab provides outbound CTAs: "Trade on neoxa.exchange" and "Register / Log In"
- Optional read-only spot price display (no swap execution in-game)
- All NMG ↔ NEOX swaps happen on neoxa.exchange with 1.5% DEX fee to LPs
- See `19-market-external-marketplace-deferred.md` for MVP scope

## Error Scenarios to Address

- Insufficient NMG balance
- Transaction timeout without confirmation
- Wrong network or unsupported wallet
- Failed burn transaction with rollback of in-game state

## Deliverable

A player-facing guide and technical specification in English that makes every wallet, deposit, withdrawal, burn, and exchange interaction clear, secure, and trustworthy.
