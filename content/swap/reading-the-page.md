---
title: Reading the page
description: What the chart, the prices, price impact, slippage, minimum received and each fee on swap.3adao.org mean, and who takes what.
section: Swap
order: 15
---

Every number on the page is derived from live data. The page shows when it was measured. A successful response is not a promise that a number is current, so check the timestamps.

## The chart: "Pool price against strategy value"

- One line is the **pool price**, what the Uniswap pool charges. The pool line is stepped, because a pool price only changes when someone trades.
- The other line is the **value**, the strategy's net asset value per token (NAV). It is smooth, because NAV is revalued continuously.
- The gap between the lines is how far the pool sits from NAV. The readout above the chart shows "pool", "value" and the gap for the point you hover over, or the latest one.
- The buttons set the time range: 24H, 1W, 1M, 3M and ALL.
- The caption says what is drawn, for example "126 drawn of 289 readings". Long periods are thinned, but every drawn point is a real reading and the highs and lows are kept.
- If the pool did not trade, the page says "The pool price is flat because the pool has not traded in this window."
- A history that is short stays short. The page says "nothing is back-filled".
- A chart point shows the strategy's value at the moment a trade was seen, so the line "can sit a little apart from the current figure above it".

## "Pool depth"

- "Total value in pool", the amount of OPS held and the USDC held.
- "Pool fee": the percentage the Uniswap pool charges on each trade.
- "Independent check": a second price source.
- If the page's depth figure and the independent source disagree it says so and adds: "Size trades conservatively until they agree."

## "What backs the token" and "Proof of reserve"

"What backs the token" shows the strategy name, "Value per token", "Tokens outstanding", "Strategy value", "Price source" and "Price taken". "Proof of reserve" shows the status, the percentage of liabilities the assets cover, and where the assets are held. See [What the swap is](/swap/what-is-the-swap).

Each box ends with a line such as "Reserves measured 3 min ago". If a figure is older than its budget, the page says: "older than its 300s budget, so treat it as indicative rather than current." The number of seconds varies.

## The quote rows

| Row | What it means |
|---|---|
| You get about (or the amount in the bottom box) | The tokens you would receive at the current pool price. |
| Route | "Uniswap v3 · Arbitrum" on the direct route. |
| Pool fee | The Uniswap pool's trading fee, as a percentage. |
| Price impact | How much worse your rate is than the pool's going rate, because your trade itself moves the price. |
| Average price | What you pay per token, as a whole: the amount you pay divided by the tokens you get. On the cross-chain route it is "Average price, all fees in" and includes every bridge and network fee. A bracket compares it with NAV, for example "(1.25% above NAV)". |
| Worst case, at minimum received | The same price if the pool moves as far as your slippage allows. |
| Minimum received | The least you will get. If the price would leave you with less, the swap does not run. This is checked on-chain, in the swap itself. |
| Network fee | Direct route: "paid by you, in ETH". Cross-chain: see below. |
| Expected time | Cross-chain only. NEAR Intents' estimate, in seconds. |

## Price impact

Price impact is shown as a percentage. The page warns, and never blocks. There is no limit on order size.

| Impact | What you see |
|---|---|
| Under 2% | Nothing extra. |
| 2% up to 10% | A caution: "Price impact is X%: at this size your rate is about X% worse than the pool's going rate. A smaller amount costs less." |
| 10% and above | "Very high price impact, X%: about Y% of the value you trade is lost to moving the pool's price. You can still go ahead; the minimum received below is the least you will get." |

From 2% up, buys also show a link to buy at NAV on optima.financial (KYC required).

The "Minimum received" does not protect you from a large impact. It is set under a quote that already includes the impact. In October 2026 the OPSBTC pool took a very large buy at a very bad price instead of refusing it. If an amount looks too big, make it smaller.

The page does refuse a trade the pool cannot fill: "The pool cannot fill this trade. Try a smaller amount." or "This is more than the pool holds: it has about X, and this trade would need all of it or more. Enter a smaller amount."

## Slippage

Slippage is how far the price may move between your quote and your swap. On the direct route you pick 0.5%, 1% or 3% under "how far the price may move before you walk away". The default is 1%. A tight setting means more failed swaps in a busy pool. A loose one means a worse worst case. The cross-chain route is fixed at 1%.

## Fees: who takes what

| Fee | Route | Who gets it | Where you see it |
|---|---|---|---|
| Pool fee | Both | The Uniswap pool, built into the price you get | "Pool fee" |
| Network fee (gas) | Direct | The Arbitrum network, paid in ETH by you | "Network fee: paid by you, in ETH" |
| Deposit gas | Cross-chain | The origin chain's network, paid by you in that chain's coin | The amber note on the review screen |
| Bridge cost | Cross-chain | The bridge, taken out of your amount | "Bridge cost" |
| Network fee, taken in USDC | Cross-chain | NEAR Intents, as one extra step in USDC | "Network fee, taken in USDC" |

On the cross-chain review the network fee row can add: "NEAR Intents reprices it until you sign: at most X USDC, paid from the USDC that would otherwise stay. The OPS you get does not change."

The steps the page builds contain an approval, a swap and one fee step added by NEAR Intents. The page refuses to ask for your signature if the steps differ from that. They contain no other payment. Where the "Pool fee" goes is a property of Uniswap, which the page does not explain.

## Warnings and error banners

- "Trading is unavailable right now": the pool list came back empty. The page will not guess a price. You can retry.
- "Trading is disabled until this loads, because sizing a trade needs live pool depth.": pool data failed to load.
- "The price history is unavailable right now. The current prices above are unaffected."
