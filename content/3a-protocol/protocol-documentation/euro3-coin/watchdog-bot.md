---
title: WatchDog Bot
description: EURO3 price stabilization bot
section: 3A Protocol
order: 114
---

The bot runs automatically to adjust the HF for Redemptions based on EURO3 under peg deviation from  EURO/USD price.

If EURO3 is within 2% away from the peg then the HF is set to 1.1.

If the EURO3 price is more than 2% under pegged then the HF for Redemptions is increased by 0.5 every check till max HF is reached. Once the EURO3 price reaches the peg within 2% deviation, the HF gets set back to 1.1.
