---
title: What the OPS swap is
nav: What it is
description: What swap.3adao.org sells, what each OPS token is and which way it moves, what the pool price and the NAV mean, and which chains it works on.
section: Swap
order: 10
---

[swap.3adao.org](https://swap.3adao.org) is a web page where you can buy "OPS" tokens: OPSBTC, OPSSOL, OPLAI and OPSAI at the time of writing. You can also sell them back. It does not run an exchange of its own. It builds the trade, shows you the numbers, and asks your wallet to sign.

3A DAO's own footer says it plainly: "This website is provided for convenience only." The trade itself is made with someone else. Read [Risks and fees](/swap/risks-and-fees) before you put money in.

## What the tokens are

The tokens are not all the same kind of product, and two of them move in opposite directions. Check which one you are buying. The page says they are issued by Optima Financial.

### Momentum strategies: OPSBTC and OPSSOL

The swap page describes these like this: they "track actively managed trading strategies", going long in uptrends and short when momentum turns, decided by a rules-based machine-learning model.

- **OPSBTC** follows a Bitcoin strategy. The page names it "Enhanced BTC Perp Momentum".
- **OPSSOL** follows a Solana strategy. The page names it "Enhanced SOL Long Short Momentum".

### AI stock baskets: OPLAI and OPSAI

These are not momentum strategies. Each is a rule-based basket of AI infrastructure stocks, built from equity perpetuals listed on Hyperliquid, and the page says the hyperscalers are deliberately left out.

- **OPLAI** moves with the basket. When these stocks rise the token rises, and when they fall it falls. It does not rotate to shorts. The page names it "Optima AI Stocks Bull".
- **OPSAI** moves against the basket. "It gains when these stocks fall and loses when they rise, though not one-for-one, so a rally in AI stocks is a loss here." The page adds that its exposure "is set by the strategy and can change". The page names it "Optima AI Stocks Bear".

Neither token should be read as moving one-for-one with the basket. A move can be larger or smaller than the basket's, depending on the exposure the strategy holds. The rules are the same for both: the constituents are screened monthly for liquidity and market cap, with equal weight as the target at each monthly reset. Live weights can differ from it.

### What the page does and does not state

For OPLAI and OPSAI the page does not state an ISIN, a custodian or a start date. For OPSSOL it gives no ISIN code or start date, though its pitch calls the token "a security with an ISIN" and says the assets are "held by BitGo". For all three, the page sends you to optima.financial for the terms.

The page lists the tokens whose pool can currently fill a buy. A token whose pool is empty is hidden. A token the page has no description for gets a box that says "This page does not yet carry a description of" that token, with a link to the issuer.

The claims about backing, custody and the prospectus come from the issuer. The page puts them under "What backs it" and "Important disclosures", and the page itself adds: "Collateralization, custody and NAV statements describe how the product is structured. They are not a guarantee of price or return." Treat them the same way. Read the issuer's own documents on [optima.financial](https://optima.financial) before you rely on them.

## Where the trade happens

Each token trades against USDC in its own Uniswap v3 pool on Arbitrum One. Your money buys tokens from that pool. There are two ways in, and the page tells you which one you are on.

| You pay with | Route | Who you trade with |
|---|---|---|
| USDC on Arbitrum | Direct. Your wallet swaps against the pool. | The Uniswap pool on Arbitrum |
| Any other token or chain the page lists | Cross-chain. You sign one message, then send a deposit. | NEAR Intents, a service run by Aurora, which then swaps in the same pool |

The page prints one of these two lines under "From (pay with)":

- "You trade directly with the Uniswap pool on Arbitrum … 3A DAO does not hold your funds and is not responsible for the pool or your transactions."
- "You trade through NEAR Intents, a third-party service run by Aurora … For a problem with a cross-chain trade, contact Intents support. 3A DAO does not hold your funds and is not responsible for that service."

How to do each: [Buy with USDC on Arbitrum](/swap/buy-with-usdc-on-arbitrum) and [Buy from another chain](/swap/buy-from-another-chain).

## Pool price and NAV

Two numbers matter, and they are not the same number.

- **The pool price** is what the Uniswap pool charges right now. It moves when people trade.
- **NAV** is the net asset value of the strategy behind the token. The page shows it as "Value per token" under "What backs the token".

Each token has its own chart, under the heading "All tokens · pool price against strategy value". One line is the pool price and the other is the strategy value. The gap between them is how far the pool sits from NAV. The page says an arbitrage bot trades against any gap to pull the pool back toward NAV. It also says the pool price is not guaranteed to equal NAV, and that a gap is no guarantee of the price you can get when you sell.

If you want to buy at NAV rather than at the pool price, the page points to the Optima app at optima.financial. The page says that route is for KYC-verified users and is not available on the swap. See [Reading the page](/swap/reading-the-page) for every number on screen.

## Proof of reserve

The "Proof of reserve" box shows the assets held against the token and a status taken straight from the data feed, for example "fully reserved". It also shows how much of the token's liabilities the assets cover and the surplus or shortfall. The status is strict. The page warns that it "flags a shortfall in at least one sub-account, however small", even when the whole book is covered. The box also shows the account so you can look at it yourself.

The status belongs to the whole report, and the report does not have to count every token. When it does not count the one you selected, the box shows no status and says "The reserve report does not cover" that token "yet, so this page makes no reserve claim for it." It then names the tokens the report does cover and links to the report. A "fully reserved" you saw for one token says nothing about another.

Proof of reserve describes the strategy's assets. It says nothing about the pool, and it does not remove the risks on the [risks page](/swap/risks-and-fees).

## Which chains

- **Arbitrum One** is where the tokens and the pool live. Buying with USDC here is the direct route.
- **Other chains** are available only through NEAR Intents, and only for the chains and tokens the page lists at the moment you look. The list changes. See [Before you start](/swap/before-you-start).

The page shows prices and the charts with no wallet connected. You need a wallet only to review and buy.
