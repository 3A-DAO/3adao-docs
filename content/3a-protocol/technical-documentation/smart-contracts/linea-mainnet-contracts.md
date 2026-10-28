---
title: Linea Mainnet Contracts
description: Contract addresses and supported collateral for the 3A protocol on Linea mainnet.
section: Protocol: Technical
order: 123
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

| Alias | Contract Address | Description |
| --- | --- | --- |
| EURO3 | [0x3F817b28Da4940F018C6b5c0A11C555ebB1264f9](https://lineascan.build/address/0x3F817b28Da4940F018C6b5c0A11C555ebB1264f9) | Stable coin pegged to EURO |
| A3A token (bridged from ethereum) | [0x3d4b2132ed4ea0aa93903713a4de9f98e625a5c7](https://lineascan.build/address/0x3d4b2132ed4ea0aa93903713a4de9f98e625a5c7) | Governance token bridged from Ethereum |
| MintableTokenOwner | [0x1BA31E955a3E1fbC8CaFfa64056c58A3e4D86082](https://lineascan.build/address/0x1BA31E955a3E1fbC8CaFfa64056c58A3e4D86082) | Controls contracts able to mint and burn EURO3 |
| Stability Pool | [0x51c3db485e3b21193636a83f05b3517f691cd68c](https://lineascan.build/address/0x51c3db485e3b21193636a83f05b3517f691cd68c) | Collects EURO3 for liquidations, users earn A3A rewards + liquidation rewards |
| Cashback Pool | [0xa1bDB7f6B749Ab887Bd712c7198aFaE6F25a3c12](https://lineascan.build/address/0xa1bDB7f6B749Ab887Bd712c7198aFaE6F25a3c12) | Collects A3A tokens, users earn Protocol Fees (EURO3) |
| Vault Factory | [0x65c6FD9B3a2A892096881e28f07c732ed128893E](https://lineascan.build/address/0x65c6FD9B3a2A892096881e28f07c732ed128893E) | The main frontend for interacting with Vaults |
| Vault Factory Zapper | [0xed35b7bbff1f59e7764d3ef053c75a538d050efa](https://lineascan.build/address/0xed35b7bbff1f59e7764d3ef053c75a538d050efa) | Facilitates the creation of Vaults and manages their operations. |
| Vault Extra Settings | [0xaaac30148e8CfE185D7F04291e95209891DB1426](https://lineascan.build/address/0xaaac30148e8cfe185d7f04291e95209891db1426) | Extra settings storage |
| Vault Factory Helper | [0x045d6078DD0d2436B67bc4050AB8F2a7E7e9B03c](https://lineascan.build/address/0x045d6078DD0d2436B67bc4050AB8F2a7E7e9B03c) | Helper for vault Factory to make easier to retrieve data |
| Vault Factory Helper V2 | [0xf4ed6867eb3080fff0c7f44ca57b3e48aca66295](https://lineascan.build/address/0xf4ed6867eb3080fff0c7f44ca57b3e48aca66295) | Helper for vault Factory to make easier to retrieve data by chunks |
| Vault Borrow Rate | [0x54F2b321a682452E4876a2c6552228Bc54Bb1Eab](https://lineascan.build/address/0x54F2b321a682452E4876a2c6552228Bc54Bb1Eab) | Helper to calculate overall borrow rate for a given vault |
| Token To Price Feed | [0xfBC5cfEb809c6352Bc4ef2FFe842f72a8769E45e](https://lineascan.build/address/0xfBC5cfEb809c6352Bc4ef2FFe842f72a8769E45e) | Manages mapping of each token for the respective price in EURO |
| Liquidation Router | [0xd18d8a82f6A294A1FAbBdFa76356f3A232fac4aE](https://lineascan.build/address/0xd18d8a82f6A294A1FAbBdFa76356f3A232fac4aE) | Handles liquidation routing: 1) Stability Pool, 2) Auctions, 3) Community liquidations |
| LastResortLiquidation | [0x24691eddc5055696B85539648Fb54cCe5DB04c9C](https://lineascan.build/address/0x24691eddc5055696B85539648Fb54cCe5DB04c9C) | Manages collateral and bad debt distribution for liquidation |
| AuctionManager | [0xe2B4B1c5D202aE49d6e5d86c1fc665393A240B4c](https://lineascan.build/address/0xe2b4b1c5d202ae49d6e5d86c1fc665393a240b4c) | Manages auctions for liquidating collateral in case of debt default |
| Owner Proxy | [0xc5241aadbd49e3e53dc6549cb7ba24e9d3559826](https://lineascan.build/address/0xc5241aadbd49e3e53dc6549cb7ba24e9d3559826) | Allows the main owner to add fine-grained permissions to other operators |
| SmartVaultDeployer | [0x4B680D2c91C1479f41Bc2f9D52582d45ad3c029A](https://lineascan.build/address/0x4B680D2c91C1479f41Bc2f9D52582d45ad3c029A) | Serves as middleware to deploy smart vaults from vaultFactory |
| SmartVaultProxy | [0x0bece260e09aeb83c7da0d06cc984ffb168f2b12](https://lineascan.build/address/0x0bece260e09aeb83c7da0d06cc984ffb168f2b12) | Allows to execute whitelisted methods for smart vaults. Such as claiming rewards. |
| BalanceGetter | [0x1d42656c2f56e81678d5a6a9965937e3a5677f4d](https://lineascan.build/address/0x1d42656c2f56e81678d5a6a9965937e3a5677f4d) | Contract to get balances of multiple ERC20 tokens for a given owner |
| USD/EURO (Price feed) | [0x06E684f6E0a601b0b8304CC2f22980a6E480c981](https://lineascan.build/address/0x06E684f6E0a601b0b8304CC2f22980a6E480c981) | Chainlink price feed to get USD/EUR |

## Supported Collateral

* WETH: <https://linea.socialscan.io/address/0xe5d7c2a44ffddf6b295a15c148167daaaf5cf34f>
* WBTC: <https://linea.socialscan.io/address/0x3aab2285ddcddad8edf438c1bab47e1a9d05a9b4>
* wstETH: <https://linea.socialscan.io/address/0xb5bedd42000b71fdde22d3ee8a79bd49a568fc8f>
* USDT: <https://linea.socialscan.io/address/0xa219439258ca9da29e9cc4ce5596924745e12b93>
* USDC.e: <https://linea.socialscan.io/address/0x176211869ca2b568f2a7d4ee941e073a821ee1ff>
* DAI: <https://linea.socialscan.io/address/0x4af15ec2a0bd43db75dd04e62faa3b8ef36b00d5>
* meUSDC: <https://linea.socialscan.io/address/0x333d8b480bdb25ea7be4dd87eeb359988ce1b30d>
* meUSDT: <https://linea.socialscan.io/address/0xf669c3c03d9fdf4339e19214a749e52616300e89>
* mewETH: <https://linea.socialscan.io/address/0xad7f33984bed10518012013d4ab0458d37fee6f3>
* mewstETH: <https://linea.socialscan.io/address/0xceed853798ff1c95ceb4dc48f68394eb7a86a782>
* mewBTC: <https://linea.socialscan.io/address/0x9be5e24f05bbafc28da814bd59284878b388a40f>

## Liquidity Pools Contracts

| Alias | Address |
| --- | --- |
| USDC.e/EURO3 (Lynex - Stable v1 pool) | [0xace89ad89b1d374fd4d198c3cc62e9ab1db717d1](https://lineascan.build/address/0xace89ad89b1d374fd4d198c3cc62e9ab1db717d1) |
| EURO3/A3A (Lynex - Fusion pool Algebra concentrated liquidity) | 0xd9bc0c51cf4cbe4d27cb942938369749f50f4ae5 |
| EURO3/A3A (Lynex - Volatile v1 pool) | [0xbde12bdbeb92b0dca3f3c37a749633a24717b24](https://lineascan.build/address/0xbde12bdbeb92b0dca3f3c37a749633a24717b24d) |
| USDC/A3A (GaugeV2) | [0x044cE3603b1A813c828E05c1305dFAb8A0d74C6](https://lineascan.build/address/0x044cE3603b1A813c828E05c1305dFAb8A0d74C69) |
