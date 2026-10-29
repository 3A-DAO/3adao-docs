---
title: Redemptions
description: Redemption is an action of depositing EURO3 into the Vaults of other users and withdrawing the equivalent value of collateral, minus the redemption fee.
section: 3A Protocol
order: 111
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

Redemption is an action of depositing EURO3 into the Vaults of other users and withdrawing the equivalent value of collateral, minus the **redemption fee**. When EURO3 is redeemed for collateral assets, the system cancels the EURO3 debt from Vaults, and the collateral asset is drawn from their collateral.

> **Note:** Redemption fees are sent to the vault owner

The value of the redeemed assets is always offset by the value of the repaid EURO3 loan ***plus the redemption fees***.  Specifically, the redeemer will have to pay back to the vault owner the value of the redeemed collateral plus the redemption fee, which at launch is set at 1%.

> **Warning:** Redemptions don't cause financial loss to the redeemed vaults!

For most assets, the redemption fee is higher than the borrowing fee making it profitable for the vault owner to reverse the redemptions by borrowing EURO3 and buying back the collateral at no additional cost. At the same time, the borrowing fee will be paid back to the cashback pool.

> **Tip:** ***Example:*** *100 EUR worth of ETH is redeemed from a vault. The redemption fee is 1%, which converts into 1 EURO3. The redeemer pays back 100 EURO3 into the vault and receives 99 EUR worth of ETH. The vault owner borrows 100 EURO3, pays 0.5% issuance fee or 0.5 EURO3 and buys back 99.5 EUR worth of ETH. They now have 100.5 worth of ETH and a loan of 100 EURO3*

**The Vaults cannot be redeemed if the** [**Health Factor**](/3a-protocol/whitelisting-criteria/risk-sensitive-parameters) **of the Vault is higher than minHF which is algorithmically determined by the protocol as a function of EURO3 price.**

**Redemption fees** are paid in EURO3 and set by the DAO governance between 0.5% and 5%.
