---
title: Vaults
description: A Vault is a smart contract used to issue and manage EURO3 loans.
section: 3A Protocol
order: 104
---

A **Vault is a smart contract** used to issue and manage EURO3 loans.

The 3A protocol supports **multi-collateral Vaults**, allowing users to utilize ***up to 5 distinct tokens*** without having to establish a separate Vault for each one.

Vaults maintain two balances: one is an asset (tokens) acting as collateral and the other is a debt denominated in EURO3. Modifying those balances by adding collateral or repaying debt changes the Vault’s health factor accordingly.

> **Note:** ***Vaults can be closed at any time by fully paying off the debt***

When a user opens a Vault, a Liquidation Reserve is applied to the debt to compensate for the gas costs in the event the Vault gets liquidated. The Liquidation Reserve is fully refundable if the Vault is not liquidated, and is given back to the user when repaying the debt. The Liquidation Reserve counts as debt and is taken into account for the calculation of a Vaults's Health Factor.

> **Warning:** **Liquidation Reserve is set at 1 EURO3**
