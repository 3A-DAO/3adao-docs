---
title: FAQ
description: Short answers to common questions about buying OPS tokens on swap.3adao.org.
section: Swap
order: 20
---

**What is the difference between OPLAI and OPSAI?** They move in opposite directions. OPLAI moves with a basket of AI infrastructure stocks. OPSAI moves against it, so a rally in those stocks is a loss on OPSAI. Neither moves one-for-one with the basket: a move can be larger or smaller. See [What the tokens are](/swap/what-is-the-swap).

**Do I need an account or KYC?** Not on the swap. The page says "No account and no KYC" for the pool route. Buying at the Optima app price on optima.financial is a separate route for KYC-verified users.

**Is there a minimum or a maximum?** The page states "No minimum and no lock-up on this page". On the cross-chain route the bridge has its own minimum, and the page tells you when your amount is below it. There is no maximum order size, only a warning for price impact and a refusal when the pool cannot fill the trade.

**Which wallets work?** Browser wallets such as MetaMask and Rabby, or your wallet's built-in browser on a phone. Only EVM wallets are covered in these guides.

**Can I pay from Bitcoin, Solana or another non-EVM chain?** The page lists some. These guides cover EVM only, and only EVM has been verified end to end. For Tron, Stellar and TON the page says paying from there isn't supported yet.

**Which chains can I pay from?** The list is loaded live and changes. See [Before you start](/swap/before-you-start). Base and Ethereum are the ones the page calls the most reliable.

**How many signatures do I need?** Direct route: two wallet transactions, an approval and the swap. Cross-chain: one message signature, then one deposit transfer. Sending leftover USDC back: one message signature.

**Does the signature cost gas?** No. The deposit transfer and the direct transactions do.

**How long does a cross-chain buy take?** The page shows an expected time in seconds. In tests it took under two minutes after the deposit. See [Buy from another chain](/swap/buy-from-another-chain).

**How long do I have to send the deposit?** The page tells you to send within 16 minutes. The deposit window closes 20 minutes after the buy is created.

**My buy says EXPIRED. Is my money gone?** If you sent nothing, nothing moved. If you sent a deposit, what happens depends on whether its transaction hash was recorded. The page records it when you use its Send button. If you sent by hand, paste the hash into the box on the page. With a recorded hash NEAR Intents keeps trying to complete the buy for up to 7 days after it was created. Without one, EXPIRED is final, and the page tells you to contact NEAR Intents support. See [Track your buy](/swap/track-your-buy).

**Where did my leftover USDC go?** It is in a NEAR Intents account linked to your wallet. You can send it back. See [Leftover USDC](/swap/leftover-usdc).

**Why did the page ask me to type the last 4 characters of an address?** The recipient is not your connected wallet. Tokens sent to a wrong address cannot be recovered.

**Can I send the tokens to someone else?** Yes, with the recipient field. You then cannot sell those tokens from this site. Only the holder can.

**Can I sell?** Yes, on the direct route, for USDC on Arbitrum. See [Selling OPS tokens](/swap/sell).

**Can I sell and receive money on another chain?** Not on this page.

**Why is the pool price different from the Optima app price?** The pool price is set by trading in a small pool. The page does not promise they match. Neither price is the NAV. NAV is the whole strategy's value, a total rather than a price per token, and the page shows it as "Strategy value". See [Reading the page](/swap/reading-the-page).

**Does 3A DAO hold my funds?** On the direct route, no. On the cross-chain route your money passes through a NEAR Intents account, run by Aurora, for a short time, and stays there if the swap does not run. 3A DAO does not run it.

**Where can I get help for a cross-chain problem?** The page links to "Intents support". Have your execution id ready.

**My wallet shows a warning about this site.** Stop. Do not click through. Contact 3A DAO.

**Is this advice?** No. See [Risks and fees](/swap/risks-and-fees).

**Where are the protocol docs?** The borrowing protocol (EURO3, vaults, the Stability Pool) is documented under [3A Protocol](/3a-protocol/welcome-to-3a).
