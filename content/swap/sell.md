---
title: Selling OPS tokens
nav: Sell
description: How to sell OPSBTC or OPSSOL for USDC on Arbitrum from your own wallet, and what the swap does not offer for selling.
section: Swap
order: 14
---

The swap can sell, but only on the direct route. You sell OPS for USDC on Arbitrum, from your wallet to the same wallet or to an address you choose.

What it does **not** do: it has no screen for selling to another chain. The cross-chain route only buys. If you want your money on another chain, sell for USDC here and move it with a tool of your own.

## Steps

1. Open [swap.3adao.org](https://swap.3adao.org) and leave "From (pay with)" on "Arbitrum · direct (Uniswap)".
2. Press the round arrow between the two boxes. Its label is "Switch to selling OPS". The card heading changes to "Sell OPSBTC" (or OPSSOL), and the top box now holds the OPS token.
3. Choose the token with the token button, enter an amount, or press "Max" to fill your exact balance. The page shows "Balance: X OPSBTC".
4. Read the quote rows. They are the same as for a buy. See [Reading the page](/swap/reading-the-page). The "Minimum received" is in USDC.
5. Connect your wallet and switch to Arbitrum One if the page asks.
6. Press "Allow Uniswap to use your OPSBTC", confirm it in your wallet, and wait while it reads "Waiting for the approval to confirm…".
7. Press "Sell" and confirm in your wallet.
8. Wait for the result. It is one of "Done: sold X OPSBTC for Y USDC.", "This trade didn't go through: it failed on-chain, so nothing was sold. Only the network fee was spent." or "We couldn't confirm this trade. Check your wallet's activity before trying again."

## Things to know before you sell

- **You get the pool price, not NAV.** The pool price can sit below or above the value per token. The "Average price" row says how far, for example "(0.40% below NAV)". The page also says that buying and redeeming at NAV is possible for KYC-verified users on optima.financial, and not on the swap.
- **Your balance is checked.** If you enter more than you hold, the page shows "You have X. Enter that or less, or press Max.", offers no approval, and the button reads "Not enough OPSBTC". Use "Max" rather than a rounded number from your wallet, because a rounded figure can be higher than your real balance.
- **Only the holder can sell.** The page warns that tokens sent to an address that is not your connected wallet cannot be sold from this site by anyone but the holder. If the recipient of a buy was a Safe or another contract, selling from here may not work.
- **A large sell moves the price.** The pool is small. The price impact warnings apply to selling too, and an amount larger than the pool can take is refused: "This is more than the pool holds: it has about X USDC, and this trade would need all of it or more. Enter a smaller amount."
- **Gas.** You pay the network fee in ETH on Arbitrum, for the approval and again for the sell.
- **Do not approve twice by impatience.** While the approval confirms, the page disables the buttons. Each extra approval is a real transaction that costs gas.
