---
title: Buy with USDC on Arbitrum
nav: Buy on Arbitrum
description: Step by step, how to buy OPSBTC or OPSSOL with USDC on Arbitrum from your own wallet, with the exact buttons and messages you will see.
section: Swap
order: 12
---

This is the direct route. Your wallet swaps USDC for OPS against the Uniswap pool on Arbitrum. There is no bridge and no quote that expires. If a swap fails, it is an ordinary failed transaction and costs only the network fee.

You need USDC on Arbitrum One and a little ETH on Arbitrum for gas. See [Before you start](/swap/before-you-start). If your wallet shows a security warning at any point, stop and contact 3A DAO.

## Steps

1. **Open [swap.3adao.org](https://swap.3adao.org).** The trade card is titled "Buy OPSBTC" or "Buy OPSSOL", after the token selected.
2. **Check "From (pay with)".** It must read "Arbitrum · direct (Uniswap)". That is the default. Under it you should see: "You trade directly with the Uniswap pool on Arbitrum".
3. **Choose the token to buy.** Press the token button in the "Buy" box. A list titled "Choose what to buy" opens. Pick OPSBTC or OPSSOL.
4. **Connect your wallet.** Press "Connect wallet". Your wallet asks you to approve the connection. If you are on the wrong network the button changes to "Switch from <network> to Arbitrum One". Press it and confirm in your wallet.
5. **Enter the amount.** Type it in the top box, which is labelled "Sell" and holds USDC. Under it you see "Balance: X USDC" and a "Max" button. "Max" fills your exact balance. If you type more than you hold, the page says "You have X. Enter that or less, or press Max." and the button reads "Not enough USDC".
6. **Read the quote.** The bottom box shows how many tokens you get. Under it are these rows: Route, Pool fee, Price impact, Average price, "Worst case, at minimum received", Minimum received and Network fee. What each one means is in [Reading the page](/swap/reading-the-page). Pay attention to Price impact. Above 2% the page shows a warning. A trade of any size is allowed, and the page does not stop you.
7. **Pick your slippage.** Under "how far the price may move before you walk away" choose 0.5%, 1% or 3%. 1% is the default. This sets "Minimum received". If the price moves further than that before your swap is mined, the swap fails and you keep your USDC.
8. **Check where the tokens go.** The line reads "OPSBTC go to your connected wallet". That is almost always right. Only press "Send to a different address" if you mean it. See below.
9. **Approve USDC.** The first time, and whenever your approval is smaller than the amount, a button reads "Allow Uniswap to use your USDC". Press it and confirm in your wallet. This approval is for the amount you entered. While it confirms the button reads "Waiting for the approval to confirm…". Do not press it again. The page waits up to two minutes. When the approval is in, the "Buy" button becomes active.
10. **Press "Buy".** The button reads "Confirm in your wallet…" while your wallet is open. Check the amounts in the wallet and confirm.
11. **Wait for the result.** The page shows "Sent. Waiting for it to confirm…" with a link to the transaction on Arbiscan. Then it shows one of these:
    - "Done: bought X OPSBTC for Y USDC."
    - "This trade didn't go through: it failed on-chain, so nothing was bought. Only the network fee was spent."
    - "We couldn't confirm this trade. Check your wallet's activity before trying again."

If you see the last message, do not press "Buy" again. Look at your wallet's activity and at the transaction link first.

## Sending the tokens to a different address

The recipient field is the most careful part of the page, because a wrong address cannot be fixed.

- It must be a plain `0x` address. Names such as `.eth` are not supported.
- The page shows the full address and never shortens it.
- It refuses the zero address, the dead address and the app's own contract addresses (the token, the pool and the router).
- A mixed-capital address that fails its checksum gets a warning to check it "character by character".
- An address that is not your connected wallet gets this warning: "You will not be able to sell these tokens from this site — only the address that holds them can sign the approval." You must then type the last 4 characters of the address ("type the last 4 characters to confirm") before the button works.
- If the address is a smart contract, such as a Safe, the page warns that selling from this site may not work.

## If it does not work

See [Troubleshooting](/swap/troubleshooting). The common causes are the wrong network, not enough ETH for gas, an amount above your balance, and a pool too small for your trade.
