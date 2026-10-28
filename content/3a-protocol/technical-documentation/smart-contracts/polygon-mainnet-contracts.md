---
title: Polygon Mainnet Contracts
description: Contract addresses and supported collateral for the 3A protocol on Polygon mainnet.
section: Protocol: Technical
order: 124
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

| Alias | Address | Description |
| --- | --- | --- |
| EURO3 | [0xA0e4c84693266a9d3BBef2f394B33712c76599Ab](https://polygonscan.com/address/0xA0e4c84693266a9d3BBef2f394B33712c76599Ab) | Stable coin pegged to EURO |
| A3A token (bridged from ethereum) | [0x58c7B2828e7F2B2CaA0cC7fEef242fA3196d03df](https://polygonscan.com/address/0x58c7B2828e7F2B2CaA0cC7fEef242fA3196d03df) | Governance token bridged from Ethereum |
| MintableTokenOwner | [0xB3857F86A95516902C953D530D3E5C29B1518a85](https://polygonscan.com/address/0xB3857F86A95516902C953D530D3E5C29B1518a85) | Controls contracts able to mint and burn EURO3 |
| Stability Pool | [0xdff76acd594101fb5e9fae176aedb21a7a1fe39](https://polygonscan.com/address/0xdff76acd594101fb5e9fae176aedb21a7a1fe39f)f | Collects EURO3 for liquidations, users earn A3A rewards + liquidation rewards |
| Cashback Pool | [0x9b5089A5a48A8F3A7f8F5CB4837249787533f85A](https://polygonscan.com/address/0x9b5089A5a48A8F3A7f8F5CB4837249787533f85A) | Collects A3A tokens, users earn Protocol Fees (EURO3) |
| Vault Factory | [0x4760847023fa0833221ae76E01Db1E483A5D20e0](https://polygonscan.com/address/0x4760847023fa0833221ae76E01Db1E483A5D20e0) | The main frontend for interacting with Vaults |
| Vault Factory Zapper | [0x8e83CA66Ec901E16BdAf137aC9eD7553E4dD95D3](https://polygonscan.com/address/0x8e83CA66Ec901E16BdAf137aC9eD7553E4dD95D3) | Facilitates the creation of Vaults and manages their operations. |
| Vault Factory Helper | [0x905784CA5246f48e8DFAF1888f9b45DCD3F11d54](https://polygonscan.com/address/0x905784CA5246f48e8DFAF1888f9b45DCD3F11d54) | Helper for vault Factory to make easier to retrieve data |
| Vault Factory Helper V2 | [0x05c5cdd1e21f7879cc77044150902c0a99940d60](https://polygonscan.com/address/0x05c5cdd1e21f7879cc77044150902c0a99940d60) | Helper for vault Factory to make easier to retrieve data by chunks |
| Token To Price Feed | [0xfBC5cfEb809c6352Bc4ef2FFe842f72a8769E45e](https://polygonscan.com/address/0xfBC5cfEb809c6352Bc4ef2FFe842f72a8769E45e) | Manages mapping of each token for the respective price in EURO |
| Liquidation Router | [0x00ff66600b35428b8eb76dc622d404c7ac27a99f](https://polygonscan.com/address/0x00ff66600b35428b8eb76dc622d404c7ac27a99f) | Handles liquidation routing: 1) Stability Pool, 2) Auctions, 3) Community liquidations |
| LastResortLiquidation | [0xe6D25543bCEFc2Dd84699B3a877ec5Bf050731Dd](https://polygonscan.com/address/0xe6D25543bCEFc2Dd84699B3a877ec5Bf050731Dd) | Manages collateral and bad debt distribution for liquidation |
| AuctionManager | [0x7aFB2EBD975345DfAC950b924fb32B757da0Fc93](https://polygonscan.com/address/0x7aFB2EBD975345DfAC950b924fb32B757da0Fc93) | Manages auctions for liquidating collateral in case of debt default |
| Owner Proxy | [0xDFEeed605b30D801b19328b1a2053B7F64BaEdeE](https://polygonscan.com/address/0xDFEeed605b30D801b19328b1a2053B7F64BaEdeE) | Allows the main owner to add fine-grained permissions to other operators |
| VaultDeployer | [0x244dce725005bfffdeee080d10ef40c75f8233f0](https://polygonscan.com/address/0x244dce725005bfffdeee080d10ef40c75f8233f0) | Serves as middleware to deploy vaults from vaultFactory |
| USD/EURO (Price feed) | [0x54F2b321a682452E4876a2c6552228Bc54Bb1Eab](https://polygonscan.com/address/0x54F2b321a682452E4876a2c6552228Bc54Bb1Eab) | Chainlink price feed to get USD/EUR |
| Vault Borrow Rate | [0x1E7224703E1B289e06F0Ff12519685fCf8E9306c](https://polygonscan.com/address/0x1E7224703E1B289e06F0Ff12519685fCf8E9306c) | Helper contract to return the borrow rate |
| PriceOrchestrator v1.0.0 | [0x30f557DdDfDE19e0102EBA00204864271eB32842](https://polygonscan.com/address/0x1E7224703E1B289e06F0Ff12519685fCf8E9306c) | Pyth Network Integration holding some price feeds |
| PriceOrchestrator v1.1.0 | [0x5db7d28dc820502739d7f8beda42ed6c11746350](https://polygonscan.com/address/0x5db7d28dc820502739d7f8beda42ed6c11746350) | This version contains unsafeGetPrice for Traditional prices (Forex + Stocks) |

## Supported Collaterals

* DAI: <https://polygonscan.com/address/0x045d6078DD0d2436B67bc4050AB8F2a7E7e9B03c>
* USDC.e: <https://polygonscan.com/address/0x2791Bca1f2de4661ED88A30C99A7a9449Aa84174>
* MATIC/WMATIC: [https://polygonscan.com/address/0x99782c90eAA2B9aB311AAa7F928322F23FfAf71](https://polygonscan.com/address/0x99782c90eAA2B9aB311AAa7F928322F23FfAf71B)
* WETH: [https://polygonscan.com/address/0xcFD9c639E84DCB9D8B9004840f12381E540d57F](https://polygonscan.com/address/0xcFD9c639E84DCB9D8B9004840f12381E540d57Fb)
* QNT: <https://polygonscan.com/address/0xD78fF234A0d5ddea664f4478D72B621715EF03E5>
* PAXG: <https://polygonscan.com/address/0x0B1d4D9F953c4113A8784f5527cf63E347C3F876>

## Liquidity Pool Contracts

| Alias | Address |
| --- | --- |
| USDC.e/EURO3 | 0xe1f9709d32db8a79ae44f66299e1a93ca84debe3 |
| EURO3/A3A | 0x58c787431f4b963ab6413d796f7bb5a40bed3bcc |
