# Prompt: GameFi 2.0 Revenue Share — Capital Providers (Section 4.2)

Act as a Game Economist documenting the Capital Provider economy for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. Miners are in-game database assets only. Rental is **server-enforced escrow via Smartnodes** — NOT trustless on-chain contracts. Canonical numbers: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`.

## Player Profile

**Capital Providers — Capital-Rich, Time-Poor**

Investors who purchase elite in-game Guild Miners and lease them to active players for passive ore income.

## Elite Miner Costs

| Rarity | Class | Cost | Supply |
|--------|-------|------|--------|
| Epic | Cyborg | 50 NMG (deposit) | Unlimited |
| Legendary | Cyborg | 200 NMG (deposit) | 500 per server epoch |

## Rental System (Server-Enforced Escrow)

1. Owner lists miner: duration, split % (e.g., 60/40), optional Gold deposit.
2. Renter accepts; deposit held in escrow.
3. Ores split automatically each mining tick per agreed ratio.
4. Owner realizes value by smelting their ore share or selling on P2P marketplace.
5. Expiry or force-recall after **24h renter inactivity** returns miner to owner.

**Do NOT describe this as trustless.** Accurate term: server-enforced escrow validated by Smartnode network.

## Passive Yield Path

Owner ore share → smelt (catalyst burn + scaled Reward Reserve payout) OR sell ores for Gold. Refer to §4.7 Win Matrix in `.whitepaper` v2.2.0 for Capital Provider minimum viable path.

## Your Task

Write a complete Capital Provider design document in English covering acquisition, rental listings, yield analytics, in-game miner marketplace (NMG/Gold prices), and security rules using canonical numbers only.
