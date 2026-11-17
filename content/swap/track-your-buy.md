---
title: Track your buy
description: What each status on a cross-chain buy means, why EXPIRED is not always final, and how to find a buy again after you close the page.
section: Swap
order: 16
---

This page is about the cross-chain route. A direct buy on Arbitrum shows only "Sent. Waiting for it to confirm…" and then "Done" or a failure. See [Buy with USDC on Arbitrum](/swap/buy-with-usdc-on-arbitrum).

After you sign, the page checks your buy's status every 12 seconds and shows it under "status". It stops checking when the status is final. If you close the tab, nothing watches your buy for you. Reopen the page, connect the wallet you signed with, and the box "Your activity" lists your buys again. The history is rebuilt from your address. The page keeps no record of you.

Each buy has an id. Keep it. The page shows it when something stops partway.

## What each status means

The wording below is what the page shows.

| Status | What the page says | What it means for you |
|---|---|---|
| CREATED | "Waiting for you to send the funds." | Signed or about to be. The deposit has not been seen. |
| SIGNED_PENDING_DEPOSIT | "Signed. Waiting for you to send the funds." | Your signature was accepted. Send the deposit. |
| DEPOSIT_PENDING | "Waiting for your deposit to arrive." | Nothing has been seen yet. Note that an unsigned buy also reads this. The page shows the deposit address only after a signature is accepted. |
| KNOWN_DEPOSIT_TX | "Your deposit has been seen and is confirming." | Wait. |
| INCOMPLETE_DEPOSIT | "Less arrived than the quote expected. It will be refunded." | You sent less than the exact amount. |
| DEPOSIT_PROCESSING or PROCESSING | "Deposit received. Bridging and swapping now." | Wait. |
| OPERATION_PENDING or OPERATION_PROCESSING | "NEAR Intents is processing the swap on Arbitrum." | NEAR Intents has the job. This status does not prove the swap is running. |
| SUCCESS | "Done. The tokens are at your chosen address." | Finished. A "Buy again" button appears. |
| REFUNDED | "Refunded to where it came from." | Your money went back. |
| EXPIRED | See below. | See below. |
| DEPOSIT_FAILED | "The deposit did not complete, so it was refunded." | |
| FAILED or OPERATION_FAILED | "This stopped after the funds moved. They are recoverable — see below." | Your USDC is in your NEAR Intents account. Follow [Leftover USDC](/swap/leftover-usdc). |

Once the status is final, a button appears. It reads "Buy again" after SUCCESS and "Start over" after anything else.

## EXPIRED is not always final

The page gives each buy a deposit window of 20 minutes from when it is created. When the window closes before the bridge has picked up a deposit, the status reads EXPIRED. If you sent nothing, nothing moved.

This is not theory. In one tested buy the deposit landed 33 seconds before the close and the status read EXPIRED at the close. Two minutes later NEAR Intents ran the swap and the status changed to SUCCESS, with the tokens in the buyer's wallet.

### What decides whether an EXPIRED buy can still complete

NEAR Intents keeps trying to complete an EXPIRED buy only if your deposit's transaction hash was recorded with it. It then keeps checking for up to 7 days after the buy was created. If no hash was recorded, EXPIRED is final, even if your deposit lands later.

- **If you pressed the page's Send button,** the page records the hash for you.
- **If you sent the deposit yourself,** paste its transaction hash into the box "Already sent it? Paste the transaction hash, so NEAR Intents can match your deposit to this buy." Do it before the window closes. When it is accepted, the page says "Recorded. NEAR Intents has this deposit's transaction hash".

What the page then says depends on what it knows:

- **Hash recorded in time:** "The deposit window closed before the bridge picked up your deposit, but this is not final: its transaction hash is recorded, so NEAR Intents keeps checking and may still complete the buy until" a date and time in UTC, 7 days after the buy was created. "Nothing more is needed from you."
- **Hash recorded only after the close:** the page says "it is not known whether NEAR Intents still picks up a hash recorded after the close", and to contact NEAR Intents support if the buy hasn't completed by that date.
- **No hash recorded:** "The deposit window closed and no deposit transaction was recorded for this buy, so it is over. If you sent nothing, nothing moved." If you did send it, the page asks you to paste the hash into the box and contact NEAR Intents support with the execution id and that hash.

In "Your activity" the page cannot tell whether a hash was recorded, so it states the rule instead and adds that "“Send it back to my wallet” under “Your activity”" returns USDC that reached your NEAR Intents account without being swapped.

For 20 minutes after the close, the page still treats an EXPIRED buy as open. It keeps checking, and it does not offer to send leftover USDC back, because that could race the swap for the same money. Do not conclude a buy failed the moment it reads EXPIRED.

If you never sent a deposit, EXPIRED is final and nothing is owed. In one tested case the reason was that the wallet had no gas coin on the origin chain, so the deposit could not be sent.

## When it is slow

If the swap stays at OPERATION_PENDING or OPERATION_PROCESSING for more than five times the "Expected time" after your deposit was seen, the page says:

"NEAR Intents is processing the swap on Arbitrum. This is taking longer than expected. Until the swap runs, your USDC is held in your NEAR Intents account on Arbitrum; you can see it under “Your activity” below."

and "Nothing more is needed from you now. This page keeps checking." and your execution id. You do not need to send anything again. A buy has stayed in this state for 48 minutes and then failed. In that case the USDC was still in the account and could be sent back.

If the status ends at FAILED or OPERATION_FAILED the page shows: "The USDC is in your NEAR Intents account on Arbitrum, which only your wallet can authorise. Send it back to your wallet under “Your activity” below."

## In "Your activity"

Each past buy shows the route, the time, the status in words, its id and, when it stopped after the money moved, the account that holds it. Only SUCCESS is shown in green. A heading above them reads "One trade stopped after the funds moved." when that applies, and explains: "The money is not lost and it is not ours. It is sitting in your own intents account — an address derived from your wallet, which only you can authorise."

Press "refresh" in that box if a new buy is missing.
