---
title: Market Risk Score
description: Scoring table for the market risk category: market cap, trading volume and volatility.
section: Protocol: Whitelisting
order: 139
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

| Category | Description | Max Points |
| --- | --- | --- |
| MarketCap (30%) | Higher than 1 billion | 30 |
|  | Less than 1 billion | Linear distribution maxed at 30 |
| Daily Trading Volume (40%) | Higher than 100 millions | 40 |
|  | Less than 100 millions | Linear distribution maxed at 40 |
| Annualized 30d Volatility (30%) | Less than 60% | 30 |
|  | Higher than 60% | Linear distribution maxed at 30 |
