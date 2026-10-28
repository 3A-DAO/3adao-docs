---
title: Liquidation
description: Automated Liquidation Mechanism
section: 3A Protocol
order: 107
---

The 3A protocol regularly updates the collateral asset prices via a decentralized data feed. When a Vault falls below the [Health Factor](/3a-protocol/whitelisting-criteria/risk-sensitive-parameters) ratio of 1, it is considered under-collateralized and is **automatically liquidated**.

> **Tip:** The liquidation mechanism is automatic, initially requiring no buyer or bidder to buy the collateral which makes the liquidation process very efficient

When a Vault gets liquidated, users keep their EURO3 but lose their collateral tokens as the debt is paid off through liquidations. Users will no longer be able to retrieve their collateral tokens by repaying the debt.

> **Warning:** **Liquidations result in a net loss for the Vault owner**
