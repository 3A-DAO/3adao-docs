---
title: Market Risk Score
description: Scoring table for the market risk category: market cap, trading volume and volatility.
section: Protocol: Whitelisting
order: 139
---

| Category | Description | Max Points |
| --- | --- | --- |
| MarketCap (30%) | Higher than 1 billion | 30 |
|  | Less than 1 billion | Linear distribution maxed at 30 |
| Daily Trading Volume (40%) | Higher than 100 millions | 40 |
|  | Less than 100 millions | Linear distribution maxed at 40 |
| Annualized 30d Volatility (30%) | Less than 60% | 30 |
|  | Higher than 60% | Linear distribution maxed at 30 |
