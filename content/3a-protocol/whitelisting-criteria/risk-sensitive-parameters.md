---
title: Risk Sensitive Parameters
description: In order to ensure that the protocol issues high-quality loans, there are a number of risk-sensitive parameters that can be tuned to trade-off security for capital efficiency.
section: Protocol: Whitelisting
order: 140
---

In order to ensure that the protocol issues high-quality loans, there are a number of risk-sensitive parameters that can be tuned to trade-off security for capital efficiency. Those limits are similar to risk limits and stress test parameters used in traditional banking systems.

**Minimum Collateral Ratio (MCR)** - represents the amount of over-collateralization required for users to borrow EURO3. It is calculated as the ratio between the value of the collateral (number of tokens \* token price) divided by the EURO3 debt. The EURO3 is always valued at 1 EURO for this calculation. The MCR is set on a per-asset basis and adjusted when market conditions change dramatically.

**Minimum Liquidation Ratio (MLR)** - represents the collateral ratio that leads to a loan being automatically liquidated. By providing a buffer between MCR and MLR, the 3A protocol can balance between a more aggressive liquidation policy for volatile assets and a capital-efficient policy for more stable assets.

Users can borrow up to the MCR, while the Vaults will be automatically liquidated if the collateral ratio falls below the MLR.

**Health Factor** estimates the safety of the user’s collateral assets against the borrowed assets and their underlying value.

$$
Health Factor = ∑(Value of Collateral (i) X Liquidation Threshold (i) )/ ∑Debt
$$

$$
Liquidation Threshold (i) = 1/ MLR
$$

> **Warning:** If the Health Factor falls below 1 then the Vault gets liquidated

> **Tip:** If the Health Factor is > **minHF** then the Vault cannot be redeemed against. **minHF** is algorithmically determined by the protocol as a function of EURO3 price
