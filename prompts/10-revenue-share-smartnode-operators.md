# Prompt: GameFi 2.0 Revenue Share — Smartnode Operators (Section 4.4)

Act as an Infrastructure Architect documenting the Smartnode network for **Terra-Forge: The Deep Core**.

**Important:** English only. No NFTs. Smartnodes are the **authoritative source of player state** and validate all mining/smelting. Canonical: `.whitepaper` v2.2.0.

## Player Profile

**Smartnode Operators — The Security Layer**

High-performance node hosts who run decentralized game infrastructure in exchange for block rewards.

## Why Smartnodes Exist

Centralized hosting creates single points of failure. Terra-Forge distributes the following across a network of Smartnodes:
- Decentralized game databases
- Multiplayer matchmaking servers
- Anti-cheat validation engines

## Smartnode Requirements

| Requirement | Value |
|-------------|-------|
| Collateral stake | 1,000,000 NEOX |
| Purpose | Ensure absolute host integrity |
| Block reward share | 45% of every L1 block reward |
| Responsibilities | Computing power, database hosting, matchmaking, anti-cheat validation |

## Your Task

Write a complete Smartnode Operator design document covering:

1. **Registration and staking:** How operators stake 1,000,000 NEOX collateral, register their node endpoint, pass health checks, and join the active roster.
2. **Distributed game database:** How player state (Gold, Ores, Ingots, miner status) is replicated across Smartnodes with failover if a node goes offline.
3. **Matchmaking server:** Handling P2P marketplace order matching and rental contract matching between owners and renters.
4. **Anti-cheat validation engine:** Server-side validation of mining speed calculations, ore accumulation rates, smelting legitimacy, and anomaly detection for impossible NMG earning rates.
5. **Block reward distribution:** How Smartnodes receive 45% of L1 block rewards proportional to uptime and performance score.
6. **Monitoring and health checks:** Heartbeat intervals, auto-deregistration after missed heartbeats, performance metrics, and a public network health dashboard.
7. **Security model:** Economic disincentive for malicious behavior through collateral, slashing conditions for downtime or validated cheating, and 51% attack resistance via distributed node set.
8. **Operator dashboard:** Node status, uptime percentage, epoch rewards, collateral balance, performance ranking, and operational logs.

## Design Goal

Smartnodes must keep the game infrastructure decentralized, secure, and censorship-resistant while providing operators with a meaningful reward for contributing computing power and integrity guarantees to the network.
