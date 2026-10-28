---
title: Dutch Auction
description: If there’s not enough EURO3 in the Stability Pool, the liquidated Vaults are offered on a Dutch auction where bidders can buy the collateral assets for EURO3.
section: 3A Protocol
order: 109
---

If there’s not enough EURO3 in the Stability Pool, the liquidated Vaults are offered on a **Dutch auction** where bidders can buy the collateral assets for EURO3.

The initial price of the Vault is set to the value of the collateral. Then, the price gradually drops over the specified time period (voted by the 3A DAO governance), enabling the bidders to realize an immediate arbitrage gain as the value of the Vault debt is usually expected to be lower than the value of the collateral assets.

> **Warning:** **If there are no bidders during the Dutch Auction, the auction is canceled and the Vault is sent to Community Liquidations**
