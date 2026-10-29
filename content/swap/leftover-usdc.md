---
title: Leftover USDC and sending it back
nav: Leftover USDC
description: Why a cross-chain buy leaves some USDC in your NEAR Intents account, how much, and how to send it back to your wallet.
section: Swap
order: 17
---

On the cross-chain route, your money passes through a NEAR Intents account on Arbitrum that is linked to your wallet. Normally it ends up as OPS in your wallet. Two things can leave USDC behind in that account:

1. **Every successful buy leaves a little.** Not all the USDC that arrives is swapped. The swap is sized to leave room for fees, and the bridge may deliver more than its guaranteed minimum. The leftover can be up to about 1% of the buy. The review screen states the range: "Between X and Y USDC will stay on Arbitrum in the NEAR Intents account linked to your wallet". After the buy, the row "Not swapped, stays in your intents account" shows the same.
2. **A buy that stopped partway.** If the status ends at FAILED or OPERATION_FAILED, or an EXPIRED buy never ran its swap, the bridged USDC stays in the account.

The account is not your wallet and it is not 3A DAO's. The page says "Only your wallet can authorise moving it." Its address is shown on the review screen and under "Your activity". The page never shortens it.

## Send it back to your wallet

The page can send the USDC back to the wallet that owns the account. It is a separate NEAR Intents transaction with its own fee, so small amounts are not worth recovering.

1. Connect the same wallet you bought with.
2. Find "Your activity". When your account holds USDC, a box says "Your NEAR Intents account holds X USDC on Arbitrum." You need at least one past buy for the box to appear. Use "refresh" if you just finished one.
3. If you see "A trade from this wallet is still in progress. Sending the USDC back becomes available once it has finished.", wait. This protects you. It also applies for 20 minutes after an EXPIRED buy, because that buy may still complete. See [Track your buy](/swap/track-your-buy).
4. Press "Send it back to my wallet". The page says "Checking the fee…".
5. Read the confirmation: "You receive X USDC at <your wallet> on Arbitrum. NEAR Intents takes a network fee of about Y USDC, and the same again stays behind in case the fee moves before it runs. You sign one message; no gas is needed."
6. Press "Sign and send" and sign the message in your wallet ("Check your wallet…"). Or press "Cancel".
7. The page shows "Sent to NEAR Intents to run." and "Running…", then "Done: the USDC is in your wallet."

If it did not run, the page says: "It didn't run, so nothing moved. The USDC is still in your NEAR Intents account."

## Things to know

- **There is no recipient field.** The money can only go back to the wallet that signs. This is deliberate.
- **The fee is about the same whatever the amount.** In October 2026 the fee was between about 1 and 3 cents. The confirmation shows the real figure. You receive the balance minus two fees, because one fee's worth stays behind in case the fee moves. If that leaves too little, the page says: "After the network fee, too little is left to be worth sending." In practice you need a balance of more than three times the fee. Dust below that cannot be recovered.
- **It needs an EVM wallet** on Arbitrum, the same one that owns the account.
- **Do not send it twice.** If the page says it could not confirm that NEAR Intents received your signature: "Your USDC stays in your NEAR Intents account unless it runs. Refresh this list in a minute before trying again."
- **One execution at a time.** If another execution for the wallet is open, the page says "Another NEAR Intents execution for this wallet is still open. Try again once it finishes or its 10 minutes pass."
- **Wallet security warning?** Stop. Do not click through. Contact 3A DAO.
