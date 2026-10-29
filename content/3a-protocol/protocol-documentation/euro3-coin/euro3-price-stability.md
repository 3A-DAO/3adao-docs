---
title: EURO3 Price Stability
description: Low volatility around the peg
section: 3A Protocol
order: 113
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

EURO3 is designed to be a low-volatility payment coin soft-pegged to the Euro. There are several mechanisms embedded into the platform to ensure a low price deviation in both directions under normal market conditions.

* **Issuance fees**: Those fees have an immediate short-term effect on the EURO3 monetary policy as the supply is impacted right away. Higher fees make new loans less attractive, decreasing the new generation of EURO3 if there is not enough demand to keep up with the supply.
* **Redemption mechanism**: Arbitrageurs can make instant gains whenever the collateral asset they get in return is worth more than the current value of the redeemed EURO3. Redemptions are triggered automatically by bots facilitating a quick peg recovery.
* **Market arbitrage**: Arbitrage bots run on exchanges to stabilize the EURO3 price.
* **Debt Issuance and Repayment**: If the price of EURO3 falls below parity by more than the issuance fee, (EURO3 < Euro) then users of the platform are incentivized to buy EURO3 in order to repay their debt. In the opposite direction, when the price of EURO3 goes above parity (EURO3 > Euro) by more than the issuance fee, users are incentivized to borrow more in order to purchase assets at a discount.
