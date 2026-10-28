---
title: Risks and fees
description: The plain risks of buying OPS tokens on the swap, what happens to your money at each stage, and what you pay.
section: Swap
order: 19
---

This is not financial advice. Tokens can lose value. Transactions on a blockchain cannot be reversed. The page itself says: "Nothing on this page is investment advice."

## What happens to your money

**Direct route (USDC on Arbitrum).** Your wallet trades with the Uniswap pool. Nothing is held on your behalf. A failed swap is an ordinary failed transaction and costs the network fee. The page says 3A DAO "does not hold your funds and is not responsible for the pool or your transactions."

**Cross-chain route.** Your money is held by a service you do not control, for a short time.

1. You sign a message. Nothing moves yet.
2. You send the deposit from your wallet on the origin chain. From here the money is handled by NEAR Intents, not by your wallet.
3. It is bridged to USDC on Arbitrum into a NEAR Intents account linked to your wallet. Only your wallet can authorise what that account does.
4. If everything works, the swap runs and the OPS goes to your recipient.

If the swap does not run, the USDC stays in that account until you send it back. This can happen after the bridge has already worked: the money arrives on Arbitrum, the swap step fails inside NEAR Intents, and the USDC waits in the account. That is what "Send it back to my wallet" is for. Do not read "recoverable" as "free": sending back costs a fee, and a very small balance cannot be recovered. See [Leftover USDC](/swap/leftover-usdc).

3A DAO does not run NEAR Intents. Aurora does. 3A DAO "takes no liability for your interactions with them or for any funds you send to them."

## Risks

- **Price risk.** The tokens follow a managed strategy. The page's own disclosures say: "Digital assets and momentum strategies carry significant risk, including loss of capital." Past performance does not indicate future results.
- **Pool price risk.** The pool price is not guaranteed to equal NAV. You may buy above NAV or sell below it.
- **A small pool moves a lot.** There is no limit on order size. The page warns about price impact and does not stop you. A very large buy fills at a much worse price than the one on screen. Typing one extra zero can cost most of what you pay. Check "Price impact" and "Minimum received" every time.
- **Recipient mistakes cannot be undone.** Receiving needs no signature, so tokens sent to an address nobody controls are gone. The page refuses the obvious mistakes but cannot know your intent.
- **Wrong token or chain.** Many chains carry two tokens with the same name. Send the exact token the page names.
- **Late deposits.** On the cross-chain route a deposit after the close time may buy nothing and be refunded minus fees, or stay in your NEAR Intents account.
- **Gas.** Without the gas coin of the origin chain in your wallet you cannot send the deposit, and the buy expires.
- **Third-party service risk.** NEAR Intents, the bridge, Uniswap and your wallet can fail or change. Cross-chain routes come and go. The page cannot promise one will work.
- **Smart-contract risk.** The tokens, the pool and the swap router are smart contracts. The page lists "Vehicle risk" for the token wrapper: "Smart-contract, custody and execution risk."
- **Issuer risk.** The strategy, its custody and its prospectus belong to the issuer. Read the issuer's documents. Statements about backing and custody "describe how the product is structured. They are not a guarantee of price or return."
- **Data risk.** Figures come from public data feeds and may be late. Check the "measured" timestamps.
- **Not every wallet works the same.** Some wallets relay transactions or pay gas in a token. If something looks wrong, stop and check.

## What you pay

| Cost | When |
|---|---|
| Pool fee, as a percentage | Every trade, on both routes. Built into the price. |
| Network fee in ETH | Direct route, for the approval and the swap. |
| Origin chain gas | Cross-chain, for your deposit. |
| Bridge cost | Cross-chain, taken from your amount. |
| NEAR Intents network fee in USDC | Cross-chain, one fee step in the buy. |
| The leftover | Cross-chain, up to about 1% of the buy may stay in your NEAR Intents account. It is yours, but it costs another fee to bring back. |
| Price impact | Every trade. Larger trades pay more. |

The page shows each of these before you sign. See [Reading the page](/swap/reading-the-page) for who gets each fee. The swap page itself adds no payment step of its own to the buy. The steps it builds are an approval, the swap and NEAR Intents' fee, and the page refuses to sign anything else.

## What these docs do not claim

The swap page uses the words "compliant investment certificates" for the OPS tokens. These docs do not describe the tokens as regulated and do not give legal or tax advice. Ask the issuer, optima.financial, for the prospectus terms.
