---
title: RedBelly Testnet Contracts
description: Contract addresses and supported collateral for the 3A protocol on the RedBelly testnet.
section: Protocol: Technical
order: 125
---

| Alias                             | Address                                    | Description                                                                                                           |
| --------------------------------- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| USDC3                             | 0xAF75626e55388B301E28E06d898FE072125f51Ae | Stable coin pegged to USDC                                                                                            |
| A3A token (bridged from ethereum) | 0xD276Ad656382492477dA5E602495A5374109F5c4 | Governance token bridged from Ethereum                                                                                |
| MintableTokenOwner                | 0x2a8D0423ad4C1276F501FcFc5EAd983a043021D2 | Controls contracts able to mint and burn EURO3                                                                        |
| Stability Pool                    | 0x28356002eD4068fCfaD9FEBa18Df2E650ee2c4e1 | Collects EURO3 for liquidations, users earn A3A rewards + liquidation rewards                                         |
| Cashback Pool                     | 0x7c1A873e501812092cCb5630CBE9eb0b8e723296 | Collects A3A tokens, users earn Protocol Fees (EURO3)                                                                 |
| Vault Factory                     | 0x321809a263790140daD760d7e01c76D350E254a3 | The main frontend for interacting with Vaults                                                                         |
| Vault Factory Zapper              | 0xf214FEA74fB85ceB26a413Ed24DDe560264756b5 | Facilitates the creation of Vaults and manages their operations.                                                      |
| Vault Factory Helper              | 0x5BE773C082846a52367ADd6B523d0776C44d2D8b | Helper for vault Factory to make easier to retrieve data                                                              |
| Vault Factory Helper V2           | 0x392585B821b8727C8fca58FAf190379bb55E3f37 | Helper for vault Factory to make easier to retrieve data by chunks                                                    |
| Token To Price Feed               | 0x4B49a43b8875c9Fa199518bB8414B98A85247eeB | Manages mapping of each token for the respective price in EURO                                                        |
| Liquidation Router                | 0x293E877797d83F842f36304F6521E85819188d07 | Handles liquidation routing: 1) Stability Pool, 2) Auctions, 3) Community liquidations                                |
| LastResortLiquidation             | 0x66d53c602DF0F911157379FE9b89E84Ac3DE5689 | Manages collateral and bad debt distribution for liquidation                                                          |
| AuctionManager                    | 0x1C67046722F9B106287D9D16991c02cFf4E3729A | Manages auctions for liquidating collateral in case of debt default                                                   |
| Owner Proxy                       | 0xcC83F222d791FE8A9b989070A6fA837a7fd12C18 | Allows the main owner to add fine-grained permissions to other operators                                              |
| Smart Vault Deployer              | 0x5361469E8E368B0B4B9094Cf300D0a8D6B606320 | Serves as middleware to deploy vaults from vaultFactory                                                               |
| Vault Extra Settings              | 0x87f51D0B2dd0d720d13dbbD7C010F4A4B8951fbb | Extra settings storage                                                                                                |
| Smart Vault Proxy                 | 0x9f2598E3E18b7325ebf97EC81c58ae2651268A00 | Reward fee to keep, fee receiver + Holds the allowed txs that can be done from a smart wallet (Such as claim rewards) |
| Vault Borrow Rate                 | 0x2A53eadc167B901D8fc5EF059626Cd6f6E453eA2 | Helper contract to return the borrow rate                                                                             |

### Supported Collaterals

| Alias | Address |
| --- | --- |
| Tokenized Apartment | 0x66a7e2ee233fc472fda370165888fd3108efc7ec |
| Tokenized Treasury Bonds | 0xec6c5f90d540bfd59657143acbb52884afe73afb |
| Tokenized Gold | 0xd2eca9eea68395426bb3ce6e5a2599ae441692c2 |
| wRedBellyNativeToken | 0xee5504180c0ac02cb28611c1776f269b7f157610 |
| Tesla Shares | 0xE75AeEDA031DC966F153656d60b6C92f70E0Fa36 |
