---
title: Vault Optimization Bot
description: Coming up in Q1 2024
section: 3A Protocol
order: 120
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

Vault Optimization Bot keeps your Vault safe. If your Health Factor (HF) falls in the danger zone the bot automatically uses your EURO3 from the Stability Pool to repay part of your debt in order to keep your HF healthy. If your HF is climbing up, the bot will borrow more EURO3 and put it into the Stability Pool in order to earn you more rewards.

Users can use default settings or customize the settings for their strategy.

> **Warning:** If the user doesn't have EURO3 in the Stability Pool, the Bot can't protect the user from liquidation.

Users can set **Low HF**, **Target HF** and **High HF**.

* if the Low HF is hit, the Bot repays the EURO3 from the Stability Pool in order to increase the HF to the Target HF
* If the High HF is hit, the Bot borrows and puts more EURO3 into the Stability Pool in order to decrease HF to the target HF

> **Note:** The next iteration of the Vault Optimization Bot will be capable of selecting the **best yield strategy** for the users by directing EURO3 to the best yield options (Stability Pool, EURO3 liquidity pools, the cashback pool, liquid staking, etc.)
