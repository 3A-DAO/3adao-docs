---
title: Dutch Auction
description: If there’s not enough EURO3 in the Stability Pool, the liquidated Vaults are offered on a Dutch auction where bidders can buy the collateral assets for EURO3.
section: 3A Protocol
order: 109
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

If there’s not enough EURO3 in the Stability Pool, the liquidated Vaults are offered on a **Dutch auction** where bidders can buy the collateral assets for EURO3.

The initial price of the Vault is set to the value of the collateral. Then, the price gradually drops over the specified time period (voted by the 3A DAO governance), enabling the bidders to realize an immediate arbitrage gain as the value of the Vault debt is usually expected to be lower than the value of the collateral assets.

> **Warning:** **If there are no bidders during the Dutch Auction, the auction is canceled and the Vault is sent to Community Liquidations**
