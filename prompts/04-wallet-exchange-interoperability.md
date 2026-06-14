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

### Wallet Connection
- Connect and disconnect wallet
- Display connected address in truncated form (e.g., G8Xp...3k91)
- Show on-chain NMG balance in the game portal header

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

### Tutorial Catalyst Subsidy (No Wallet Required)
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
