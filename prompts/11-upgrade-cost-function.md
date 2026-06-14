# Prompt: Anti-Inflationary Token Sinks — Progression & Upgrade Cost Function (Section 5.1)

Act as a Game Economist documenting the tool upgrade system for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. 80% NMG → on-chain burn; 20% → Game Treasury (NMG). Canonical: `.whitepaper` v2.2.0 and `16-economy-numbers-bible.md`.

## Purpose

Tool upgrades increase mining drill efficiency (L_tool from level 1 to level 2), directly improving the mining speed equation. Upgrade costs serve as a major NMG and Gold sink, preventing inflation and creating continuous deflationary pressure.

## Upgrade Cost Formula

Cost to upgrade a tool from level L_tool to L_tool + 1:

**Cost_upgrade = (L_tool)² × φ × NMG + (L_tool)^1.5 × θ × Gold**

## Parameters

- φ (NMG scaling multiplier) = 1.50
- θ (Gold scaling multiplier) = 25.00
- L_tool ranges from 1 to 2 (maximum drill level)

## Example: Upgrade from Level 1 to Level 2

- NMG cost: (1)² × 1.50 = 1.50 NMG
- Gold cost: (1)^1.5 × 25.00 = 25.00 Gold
- Total: 1.50 NMG + 25.00 Gold

## NMG Burn Split on Upgrades

- 80% of NMG spent on upgrades is burned instantly on-chain
- 20% of NMG spent on upgrades is held in the Game Treasury for community programs and buybacks

For the level 1 to 2 upgrade example:
- 1.20 NMG burned permanently
- 0.30 NMG allocated to Game Treasury

## Your Task

Write a complete tool upgrade system design document covering:

1. The upgrade cost formula and how quadratic NMG scaling makes higher levels exponentially expensive.
2. The dual-currency cost structure: NMG burn (deflationary) plus Gold cost (accessible to time-rich players).
3. The 80/20 burn-to-treasury split and how treasury accumulation funds the automated buyback program.
4. The upgrade flow from player initiation through NMG burn confirmation and tool level increment.
5. UI requirements: current vs next level preview, exact cost breakdown, burn vs treasury allocation display, and new mining speed preview after upgrade.
6. How upgrades interact with the mining speed equation (increasing L_tool improves Φᵢ).
7. Extensibility for future tool levels beyond level 2 if the maximum is increased.

## Design Goal

Upgrades must feel meaningful (visible mining speed improvement) while serving as a reliable, scaling token sink that removes NMG from circulation and funds treasury stability mechanisms.
