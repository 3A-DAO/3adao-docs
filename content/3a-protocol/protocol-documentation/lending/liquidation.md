---
title: Liquidation
description: Automated Liquidation Mechanism
section: 3A Protocol
order: 107
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

The 3A protocol regularly updates the collateral asset prices via a decentralized data feed. When a Vault falls below the [Health Factor](/3a-protocol/whitelisting-criteria/risk-sensitive-parameters) ratio of 1, it is considered under-collateralized and is **automatically liquidated**.

> **Tip:** The liquidation mechanism is automatic, initially requiring no buyer or bidder to buy the collateral which makes the liquidation process very efficient

When a Vault gets liquidated, users keep their EURO3 but lose their collateral tokens as the debt is paid off through liquidations. Users will no longer be able to retrieve their collateral tokens by repaying the debt.

> **Warning:** **Liquidations result in a net loss for the Vault owner**
