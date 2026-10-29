---
title: Buy from another chain
description: How to buy OPSBTC or OPSSOL with a token on another chain using one signature and one deposit, what happens behind the scenes, and how long it takes.
section: Swap
order: 13
---

With this route you pay with a token on another chain, for example USDC on Base. You sign one message, then you send one deposit from your wallet. NEAR Intents, a service run by Aurora, moves the money to Arbitrum as USDC, swaps it for OPS in the Uniswap pool, and sends the OPS to the address you chose.

3A DAO does not run NEAR Intents and the page says it is "not responsible for that service". For a problem with a cross-chain trade the page points you to "Intents support". Read [what happens behind the scenes](#what-happens-behind-the-scenes) before you start.

Before you start, read [Before you start](/swap/before-you-start). You need the origin token, and a little of that chain's gas coin in the same wallet. If your wallet shows a security warning at any point, stop and contact 3A DAO.

If the page says "Buying from other chains is paused for now. Pay with USDC on Arbitrum.", this route is switched off at the moment. Use [the direct route](/swap/buy-with-usdc-on-arbitrum).

## Steps

1. **Open [swap.3adao.org](https://swap.3adao.org)** and press the "From (pay with)" box.
2. **Choose the chain.** The dialog asks "Pay from which chain?". Search or pick one. Once your wallet is connected, chains your wallet cannot sign for are greyed out.
3. **Choose the token.** The dialog asks "Which token on <chain>?". The list is not fixed. On Arbitrum, USDC is labelled "direct (Uniswap) — no bridge" and every other Arbitrum token is "via NEAR Intents".
4. **Check the route line.** It must read "You trade through NEAR Intents, a third-party service run by Aurora".
5. **Enter the amount** of the origin token. If your wallet is already on that chain the page shows "In your wallet on Base: X USDC". If you enter more than that it warns: "Your wallet has X, less than this amount. Lower it, or send the deposit from another wallet." The page only knows your balance when the wallet is already on the origin chain.
6. **Read the indicative quote.** A box labelled "indicative quote" shows "You get about", "Minimum received", "Price impact", the prices and "Expected time". It works without a wallet and says "connect a wallet to buy". It is a test run: it is not a firm quote.
7. **Set "tokens go to".** The recipient field fills with your connected wallet. Change it only if you mean to. The same checks as the direct route apply. See [Buy with USDC on Arbitrum](/swap/buy-with-usdc-on-arbitrum#sending-the-tokens-to-a-different-address).
8. **Connect your wallet.** Press "Connect an Ethereum wallet". If no browser wallet is found the button says "No browser wallet found".
9. **Press "Review".** The button reads "Checking…" while the page makes test runs with NEAR Intents. Nothing is created yet and no funds move.
10. **Read the review screen.** It is headed "what will happen":
    - "Bridged to Arbitrum, at least": the USDC that must arrive.
    - "Swapped for OPS": the part of it that is swapped.
    - "Price impact", "You get about" and "You receive at least".
    - The fee rows. See [Risks and fees](/swap/risks-and-fees).
    - "Expected time" in seconds.
    - A note about the USDC that will not be swapped. See [Leftover USDC](/swap/leftover-usdc).
    - In amber: "After you sign, you send the USDC yourself, from your wallet on Base, within 6 minutes. That transfer is a normal Base transaction, so your wallet needs a little ETH on Base to pay its network fee. Check before you sign."
11. **Press "Confirm and sign".** The button reads "Check your wallet…" and the page says "Signing… approve the message in your wallet." Your wallet shows a message to sign. There is no gas cost for this. If the review is more than a minute old, the page does not sign. It fetches a new quote and says: "This quote was more than a minute old, so we fetched a fresh one and nothing was signed. The price may have moved: check the figures above, then confirm again."
12. **Send the deposit.** Only after your signature is accepted does the page show "send the funds", with the exact amount and a deposit address. Send exactly that amount, on that chain, of that token. Two ways:
    - Press the button "Send <amount> <token> from your wallet". Your wallet switches to the origin chain and asks you to confirm one transfer.
    - Or copy the address with "Copy" and send it yourself. The page also prints the token's contract on that chain. Many chains have two tokens with the same name, so check it.
13. **Wait.** After the transfer the page says "Sent from your wallet. Don't send it again." and shows the status. See [Track your buy](/swap/track-your-buy).

The deposit address is for this one transfer. Send it by the time shown ("Send it by 12:34 UTC"). The page counts that time down and, near the end, says "too late — do not send". Do not send after that.

## Why the page shows the deposit address only after you sign

Your signature is what allows your NEAR Intents account to run the swap. A deposit that arrives with no signature has nothing authorised to act on it. That is why the address stays hidden until the signature is accepted. If your wallet declines the signature the page says: "You declined the signature, so nothing can receive funds. Sign again when ready." Never send money to an address from another source that claims to be for this buy.

## What happens behind the scenes

In plain words:

1. **Test runs.** When you press "Review" the page asks NEAR Intents for quotes without creating anything. It works out the fee and how much USDC can safely be swapped. It makes a second check with the real numbers and, if the quote moved, a small re-size.
2. **Your NEAR Intents account.** Every wallet has an account on Arbitrum that NEAR Intents runs for it. The page calls it "the NEAR Intents account linked to your wallet". Only your wallet can authorise anything in it.
3. **The steps.** The buy is a list of steps for that account: approve USDC for the swap, swap USDC for OPS in the pool and send the OPS to your recipient, then one fee step added by NEAR Intents. The page checks the list before it asks for your signature. It refuses anything that is not exactly the buy you reviewed plus one fee step.
4. **Your signature** authorises those steps.
5. **Your deposit** goes to a deposit address on the origin chain. NEAR Intents sees it and bridges it to USDC on Arbitrum, into your account.
6. **The swap runs** and the OPS goes to your recipient. If the swap is set for a minimum amount of OPS and the pool price moves too far, the swap does not run at all.

## How long it takes

The review screen shows an "Expected time" in seconds, taken from NEAR Intents. In October 2026 one tested buy finished in under two minutes after the deposit. Another, deposited very near its deadline, first read EXPIRED and was completed a couple of minutes later (see [Track your buy](/swap/track-your-buy)). The page's own text says the status changes "usually within a minute or two" after the deposit is seen.

You have a limited window to send the deposit. A quote closes 10 minutes after it is created. The page tells you to send within 6 minutes, because the bridge and the swap must both finish before the buy closes. A deposit that arrives too late "may buy nothing and stay in your NEAR Intents account on Arbitrum, or be refunded minus fees".

## One buy at a time

Only one open buy is allowed per wallet. If you leave a buy unsigned or half done, the page may say: "This wallet already has an unfinished buy with NEAR Intents, and only one can be open at a time. Nothing has been charged." See [Troubleshooting](/swap/troubleshooting).

## Slippage here

The cross-chain route has no slippage setting. It is fixed at 1%.
