---
title: Welcome to 3A
description: Financial freedom at your fingertips
section: 3A Protocol
order: 101
---

3A is a decentralized lending protocol offering efficient leverage with no recurring interest for crypto and on-chain Real World Assets, ensuring enterprise-grade security. It is non-custodial and permissionless, enabling users to leverage their long position, which is particularly attractive for yield-bearing assets like liquid-staked tokens, LP tokens, tokenized bonds and treasuries.

Users deposit whitelisted crypto-assets (e.g., stETH) as collateral into a smart contract called vault, allowing them to mint and withdraw EURO3 stablecoin, pegged to the Euro. EURO3 is then used to buy and deposit more collateral. In order to avoid liquidation, vaults must maintain a required  [Health Factor](/3a-protocol/whitelisting-criteria/risk-sensitive-parameters) (HF) determined by the 3A data-driven risk model.

In addition to the collateral, the loans are secured by the [Stability Pool](/3a-protocol/protocol-documentation/lending/stability-pool) which contains EURO3 tokens staked by fellow borrowers acting as guarantors.

3A protocol solves four critical problems for users and protocols :

* **On-demand, low-cost liquidity** by borrowing against a wide range of tokens at zero interest rate
* **Deep liquidity on DEXs** without the need to incentivize or pay the other side of the liquidity pools
* **Sustainable yields** and **cashback options** in a safe and secure environment
* **Treasuries management** with smart capital allocation

> **Tip:** **3A Self-Sovereign Liquidity -** Cost and capital efficient solution to protocol-owned liquidity

### Who should use 3A?

* **Blockchain protocols** in need of low-cost and on-demand deep liquidity for their tokens trading in DEX pools
* **Users** who want to earn yield and access liquidity by borrowing against their own tokens
* **Treasuries** who want to diversify their concentrated portfolios without selling tokens

### EURO3 and A3A tokens

**EURO3** is the Euro-pegged stablecoin used to pay out loans on the 3A protocol.  It is tradable and exchangeable and users can always use 1 EURO3 to pay back 1 Euro worth of their loan directly on the 3A platform. Additionally, users can redeem 1 EURO3 for 1 Euro worth of collateral from vaults with HF \<minHF.  Learn more about the [stability mechanism](/3a-protocol/protocol-documentation/euro3-coin/euro3-price-stability).

**A3A utility token** is used to orchestrate the 3A ecosystem. The value that comes through the 3A platform is returned to the A3A token holders and can be used to automatically repay 3A loans by users who stake A3A. The total A3A supply is capped at 1,000,000,000 tokens. For more information on how the tokens are allocated and released over time, please refer to [A3A Token](/3a-protocol/protocol-documentation/a3a-token) section

### Collateral tokens accepted by 3A

3A DAO's data-driven Risk Model approves whitelisted assets with collateral ratios ranging from 105% to 500%. It takes into account DeFi market volatility and liquidation risks.

You can find more details about the [Risk Methodology](/3a-protocol/whitelisting-criteria/risk-methodology) and the current whitelisted tokens [here](/3a-protocol/whitelisting-criteria/whitelisted-tokens).

### Getting started with 3A

To borrow EURO3, all you need is a wallet (e.g. MetaMask) with whitelisted tokens that are used as collateral.

To become a Stability Pool depositor or A3A staker, you need to have EURO3 and/or A3A tokens. EURO3 can be borrowed by opening a Vault while A3A can be earned as a Stability Pool depositor or as [referral rewards](/3a-protocol/community-rewards/referral-system).

> **Tip:** **EURO3 and A3A tokens can also be bought on Uniswap**

### Platform fees

3A protocol offers interest-free loans. However, there is a one-off fee when EURO3 is borrowed, and when EURO3 is redeemed:

* For borrowers, there is an **issuance fee** on loans as a percentage of the drawn amount.  The fee is paid in EURO3, added to the loan right from the beginning, and is calculated between 0.5% and 5%, depending on the collateral type and the current market demand for EURO3.
* For redeemers, there is a **redemption fee** on the amount paid to users when exchanging EURO3 for vault collateral in vaults with HF \<min HF which is algorithmically calculated based on the value of EURO3. The redemption fee is set by the DAO governance process and is paid in EURO3.

> **Note:** **Repaying the debt is free of charge**

### Key innovations

* [**Cashbacks**](/3a-protocol/protocol-documentation/a3a-token/a3a-staking-and-cashbacks) - Token holders can stake their A3A tokens to receive discounts on the fees charged by the protocol and to repay their EURO3 loans. Cashback cannot be received without using the platform.
* **Real World Assets** - Tokenized real-world assets require liquidity and a means to generate sustainable yields. 3A's data-driven risk model will whitelist a broad range of tokenized real-world assets.
* [**Premium Services** ](/3a-protocol/protocol-documentation/premium-services)**-** The Premium Bots offered by the 3A protocol simplify user experience, lower risks and increase yield options. Arbitrage, vault optimization, and liquidation bots assist users throughout their journey on the platform.

### Risks of using the 3A platform

There are two scenarios under which users may lose part of their funds:

* **Vault liquidation** - if a vault gets liquidated, the borrower can still keep their borrowed EURO3, but the Vault will be closed and the collateral will be used to compensate Stability Pool depositors.
* **Stability Pool depositors** may have their EURO3 used to repay debt from liquidated borrowers. Since liquidations are triggered before the collateral value reaches the value of the debt, the Stability Pool participants will receive additional tokens to compensate for the EURO3 burned. However, in very volatile markets if the tokens continue to drop in price before users decide to sell the collateral tokens, they may incur losses.

> **Note:** Please note that the price of EURO3 can deviate slightly from the Euro in both directions under certain market conditions. See [Stability Mechanism](/3a-protocol/protocol-documentation/euro3-coin/euro3-price-stability) for more details.

Although the system is diligently audited, a hack or a bug that results in losses of users' funds can never be fully excluded (see Disclaimer)

## Governance

3A protocol is governed by the [3A DAO LLC](/3a-protocol/governance/3a-dao)
