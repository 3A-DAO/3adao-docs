---
title: Before you start
description: What you need before you buy OPSBTC or OPSSOL on the swap - a wallet, the right chain, gas, and what you will be asked to sign.
section: Swap
order: 11
---

Do these checks first. Most stuck buys come from skipping one of them.

## A wallet

- **On a computer:** install a browser wallet such as MetaMask or Rabby, then reload the page. The page says: "On desktop, install MetaMask or Rabby and reload."
- **On a phone:** open the swap inside your wallet's own browser. The page says MetaMask, Rainbow and Coinbase Wallet all have one.
- If the page shows "No wallet detected in this browser.", it cannot find a wallet. Fix that first.

The swap connects to a browser wallet. You do not need an account, and the page says there is "No account, no minimum, no lock-up". Cross-chain buys are covered below.

You can look at prices, the chart and a quote without connecting. The page says: "Quotes are test runs: nothing is created and no funds move. A wallet is needed only to Review and buy."

## If your wallet shows a security warning

Stop. Do not click through it. Do not approve, sign or "connect anyway". Close the page and contact 3A DAO, then wait for an answer. A warning on a page that asks for approvals is a reason to stop, whatever the reason turns out to be.

Check that the address bar says `swap.3adao.org` exactly. Do not use a link from a message you did not ask for.

## Which route fits you

| You hold | Use | Guide |
|---|---|---|
| USDC on Arbitrum | The direct route | [Buy with USDC on Arbitrum](/swap/buy-with-usdc-on-arbitrum) |
| A token on another EVM chain (Base, Ethereum and others) | The cross-chain route | [Buy from another chain](/swap/buy-from-another-chain) |
| A token on Arbitrum that is not USDC | The cross-chain route (the picker marks it "via NEAR Intents") | [Buy from another chain](/swap/buy-from-another-chain) |

## Which chains and tokens are accepted

You choose in the box called "From (pay with)". The list of chains and tokens is loaded from NEAR Intents each time you open the page. It is not fixed, and a token being listed does not mean a quote is available.

On 20 October 2026 the 3A team measured small test quotes. Base, Ethereum, Gnosis, Berachain and Plasma gave quotes for the tokens tried. BNB Chain, Optimism, Polygon, Avalanche, Scroll, Monad and X Layer refused every token. That list changes, so do not rely on it. When a quote is refused the page says so and nothing is created. The page's own advice is: "try another token or chain (Base and Ethereum are the most reliable), or pay with USDC on Arbitrum."

The page also lists chains that are not EVM chains. To pay from one you need a wallet of that kind. The code supports a Solana wallet (Phantom or Solflare) and a NEAR wallet (Sender or Meteor). Only the EVM path has been verified end to end in the code. For Tron, Stellar and TON the page says: "Paying from this chain isn't supported yet". These guides cover EVM wallets only.

## Gas: the fee your wallet pays

Gas is separate from the price of the tokens. Keep a little of the right coin in the wallet.

- **Direct route:** you send two transactions on Arbitrum, one approval and one swap. The page shows "Network fee: paid by you, in ETH". You need ETH on Arbitrum.
- **Cross-chain route:** you sign one message, which costs no gas. Then you send the deposit yourself from the origin chain, and that transfer is a normal transaction on that chain. You need that chain's own coin there. The review screen names it. For example it is ETH on Base, Ethereum, Optimism and Scroll, and xDAI on Gnosis. The page warns: "your wallet needs a little ETH on Base to pay its network fee. Check before you sign." A buy on Base was once signed with no ETH on Base. The deposit could not be sent and the buy expired.

## What you will sign

| Action | What your wallet shows | Gas? |
|---|---|---|
| Direct buy or sell: approval | An "approve" transaction for the exact amount you entered | Yes, ETH on Arbitrum |
| Direct buy or sell: swap | A Uniswap swap transaction | Yes, ETH on Arbitrum |
| Cross-chain buy: authorisation | One message signature | No |
| Cross-chain buy: deposit | A plain transfer of your token on the origin chain | Yes, on the origin chain |
| Sending leftover USDC back | One message signature | No |

The message signature in the cross-chain route is not readable as amounts. It authorises your NEAR Intents account to run prepared transactions for you. The page checks the message before it asks your wallet to sign. It refuses anything that is not for your wallet or that carries more actions than the buy has steps. It cannot show you the amount or the recipient inside the message, so check those on the review screen before you press "Confirm and sign".

## The recipient

Tokens go to an address you choose. By default it is your connected wallet. If you choose another address, the page warns you and asks you to type its last four characters. Read [Buy with USDC on Arbitrum](/swap/buy-with-usdc-on-arbitrum) for how this works. A wrong recipient cannot be undone by anyone.
