---
title: Troubleshooting
description: What to do when a buy is stuck, refused, expired or left USDC behind, with the messages the swap page shows and what each one means.
section: Swap
order: 18
---

Start with the message on the page. Find it below. In every case: if your wallet shows a security warning, stop and contact 3A DAO. Do not click through.

## Before anything is signed

**"No wallet detected in this browser."** The page cannot find a wallet. On a phone, open the page inside your wallet's own browser. On a computer, install MetaMask or Rabby and reload.

**The button says "Switch from <network> to Arbitrum One".** Your wallet is on another network. Press the button and confirm in your wallet. This only applies to the direct route.

**"Not enough USDC" (or OPSBTC).** The amount is above your balance. Press "Max". The page does not offer an approval for more than you hold.

**"Trading is unavailable right now".** The pool list came back empty. The page will not guess a price. Press "Try again" later. Contracts and reserves shown on the page are not affected.

**"Buying from other chains is paused for now. Pay with USDC on Arbitrum."** The cross-chain route is switched off. Use [the direct route](/swap/buy-with-usdc-on-arbitrum). Recovery of money already in a NEAR Intents account still works.

**"NEAR Intents is not quoting payments from <chain> with this token right now."** The chain or token has no route at the moment. Nothing was created. Try another token or chain. The page names Base and Ethereum as the most reliable, or pay with USDC on Arbitrum. A chain that worked yesterday can stop.

**"NEAR Intents has a temporary minimum of $X for payments from <chain>."** Use a larger amount, or another chain.

**"That amount is below the bridge's minimum. Send at least X from <chain>."** Raise the amount.

**"This amount is too small: the bridge would deliver at least X USDC but the network fee alone is Y USDC."** The fee would eat the trade. Use a larger amount.

**"The connected wallet cannot receive a refund on <chain>."** The wallet you connected does not match the chain you picked. Connect a wallet for that chain.

**"Too many requests. Wait a minute and try again."** (it appears after "NEAR Intents refused this"). The page limits how many quote and buy requests one network address can make in a minute, about 20 for the requests that need NEAR Intents. Every quote you type, and every review, counts. People behind the same network share the count. Wait a minute and try again. Do not refresh repeatedly.

**"NEAR Intents refused this" with nothing after it.** The request was refused and the page has no reason to show. The message always adds that nothing was created or signed and no funds moved. Wait, then try again with a different amount or token.

**"The bridge service didn't answer…"** NEAR Intents or its connection failed. Before you sign, nothing was created. Try again in a moment. Read the wording carefully if it appears at the sign step: "Don't send any funds: the deposit address only appears once the signature is confirmed."

**"This quote was more than a minute old, so we fetched a fresh one and nothing was signed."** Check the new figures and press "Confirm and sign" again.

**"The bridge quote moved while we checked it…"** or **"The bridge quote kept moving while we checked it, so we stopped…"** The bridge price changed between the page's checks and a safe swap size could not be found. Nothing was created or signed. Press "Review" again.

**"The swap would spend X USDC, but only Y USDC is left after the network fee, so it would fail after signing. Nothing was signed."** The page refused to sign a buy that could fail after your deposit. Review again for a fresh quote.

**"The pool cannot fill this trade. Try a smaller amount."** or **"This is more than the pool holds…"** The pool is too small. Use a smaller amount.

## Your wallet is blocked: "already in progress"

"This wallet already has an unfinished buy with NEAR Intents, and only one can be open at a time. Nothing has been charged."

NEAR Intents allows one open buy per wallet. A buy you started but did not finish, for example by declining the signature, holds that slot until its quote closes. That is up to 10 minutes after it was created. Another reason is that a buy was refused after NEAR Intents had created it. The page says when your wallet is free, for example "An unfunded buy closes at 13:36 UTC". Wait until then and start a new buy. If you declined the signature and the same review is still open, press "Confirm and sign" again. The page signs the same buy instead of creating a second one, as long as the quote has more than a minute left.

## At the signature

**"You declined the signature, so nothing can receive funds. Sign again when ready."** You pressed reject. Nothing was sent. The deposit address is not shown, and you must not send money.

**"Your signature wasn't accepted, so nothing can receive funds. Don't send anything."** Start again.

## At the deposit

**"Your wallet doesn't have <chain> yet. Add <chain> to it, then press Send again."** Your wallet does not know the chain. The page does not add chains for you. Add the chain in your wallet from its own list, then press the button again.

**"Your wallet is not on <chain>. Switch it to <chain>, then press Send again."**

**"Your wallet doesn't have enough ETH on Base for the network fee, or not enough USDC. Nothing was sent."** (with your chain and token). Add gas or lower the amount. Nothing was sent.

**"Your wallet has X, less than the Y this buy needs, so nothing was sent."** Send exactly the amount from another wallet before the close time, or let this buy close and start a smaller one.

**"You declined it in your wallet, so nothing was sent."** Press the button again or send by hand.

**"Too little time is left for the bridge and the swap to finish before this buy closes… so don't send now."** Do not send. Wait for it to close and start a new buy.

**You sent the deposit but the status does not change.** Wait. After your deposit is seen the page usually updates within a minute or two. Do not send again. If your wallet sent it, the page says "Sent from your wallet. Don't send it again." A second transfer would only be refunded, minus fees.

## After the deposit

- **EXPIRED:** it is not always final. See [Track your buy](/swap/track-your-buy).
- **FAILED or OPERATION_FAILED:** the USDC is in your NEAR Intents account. See [Leftover USDC](/swap/leftover-usdc).
- **Stuck at "NEAR Intents is processing the swap on Arbitrum":** wait. After a long time the page says "This is taking longer than expected" and shows your id. The USDC is in your account and can be sent back once the trade has finished.
- **"Send it back to my wallet" is missing or says "A trade from this wallet is still in progress":** an older trade is still open. EXPIRED buys count as open for 20 minutes.
- **"After the network fee, too little is left to be worth sending.":** the leftover is too small to recover.

## A direct trade failed

**"This trade didn't go through: it failed on-chain, so nothing was bought. Only the network fee was spent."** The usual cause is that the price moved beyond your slippage. Try again, maybe with a smaller amount or higher slippage.

**"We couldn't confirm this trade. Check your wallet's activity before trying again."** Look at the transaction link. Do not repeat a trade that may have landed.

**"We couldn't confirm the approval yet. If your wallet shows it confirmed, reload the page before approving again."** Reload, then check "Allow Uniswap…" is no longer offered.

**Your wallet says "likely to fail" or "not enough ETH" although you have ETH.** Some wallets cannot price a transaction they cannot simulate, and show a misleading fee message. One real case was an amount slightly above the holder's balance. Check the amount first.

## Still stuck

Money in a cross-chain trade is held by NEAR Intents. For a problem with one, the page links to "Intents support". Keep your execution id (shown on the page and under "Your activity") and your wallet's transaction hash. For a problem with the swap page itself, contact 3A DAO. Do not share your seed phrase or private key with anyone, for any reason.
