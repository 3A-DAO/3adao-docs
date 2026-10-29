---
title: Stability Pool
description: The Stability Pool is the first line of defense in maintaining system solvency.
section: 3A Protocol
order: 106
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

The Stability Pool is the first line of defense in maintaining system solvency. It acts as the source of liquidity to repay debt from liquidated Vaults, ensuring that the total EURO3 supply always remains backed.

The Stability Pool is funded by Stability Providers depositing EURO3 to receive liquidated tokens and A3A rewards. When liquidations occur, the Stability Providers lose a pro-rata share of their EURO3 deposits, while gaining a pro-rata share of the liquidated collateral.

As Vaults are liquidated at a collateral-to-debt ratio higher than 100%, it is expected that Stability Pool Providers will receive a greater Euro-value of collateral relative to the debt they pay off.

> **Note:** **Stability Providers may receive any whitelisted collateral assets during liquidations.**

If a user borrows against their own ETH tokens and decides to deposit some of the borrowed EURO3 into the Stability Pool, they will participate in all liquidations, not just ETH. The users who do not wish to get exposed to certain assets can swap those assets immediately after the liquidation.

> **Warning:** **There is no minimum lockup duration for Stability Pool deposits**
