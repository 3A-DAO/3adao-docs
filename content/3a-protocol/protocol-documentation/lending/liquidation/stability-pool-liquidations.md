---
title: Stability Pool Liquidations
description: When a Vault is liquidated, the amount of EURO3 corresponding to the remaining Vault debt is burned from the Stability Pool’s balance to repay its debt.
section: 3A Protocol
order: 108
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

When a Vault is liquidated, the amount of EURO3 corresponding to the remaining Vault debt is burned from the Stability Pool’s balance to repay its debt. In exchange, the **entire collateral** from the Vault is pro-rata distributed among Stability Providers.

Stability Providers can immediately withdraw the collateral received from liquidations and sell it to reduce their exposure to collateral tokens.
