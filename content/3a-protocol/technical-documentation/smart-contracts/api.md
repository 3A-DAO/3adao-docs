---
title: API
description: The 3A Borrowing Protocol API is engineered to facilitate seamless interaction between integrators and the core protocol contracts.
section: Protocol: Technical
order: 126
---

## Retrieves core protocol contract addresses

`GET` `https://api-testnet.3adao.org/chain`

### 200: OK JSON Format

```json
{
"jsonData": {
"lastResortLiquidation": "0xF126bB7C214B1cDBde7f4296Da2Da5Fc99e34F27",
"auctionManager": "0xc3E52ebA21517c59BEdA53A1C760fdf2fb2C0025",
"vaultFactory": "0x050FAc481D26BDd477e121c04e5b059eDFd9F42f",
"liquidationRouter": "0xd14A6F345E44B8c061b63f6A79DA47F148082F54",
"a3aToken": "0x5D402E1Cf27769de037fDed4CdC1Aff2B0ce2208",
"mintableTokenOwner": "0xfd9f0EEa6a617C2D0Ab9656Fd6cf8aC5ED53Fd0C",
"stabilityPool": "0xaE5756207501459a9A72F2e4d06B219e146918dB",
"stableCoin": "0x25D50b4A9C4301ED18F832dD0ca002b3006D5ef0",
"a3aStaking": "0xED6aBF8eb45921E3ec462cD09e9DcDc13b4BA82A",
"rpc": "https://rpc.buildbear.io/urban-zam-wesell-f93d4545",
"chainId": "10801"
}
}
```

## Get overall protocol statistics

`GET` `https://api-testnet.3adao.org/protocolStats`

### 200: OK JSON Format

```json
{
"vaults": 68,
"totalDebt": "500.0",
"tvl": "1208.31",
"uniqueUsers": 0,
"borrowRate": "0.005",
"redemptionRate": "0.005",
"maxTokensPerVault": "5"
}
```

## Retrieves core protocol supported collaterals

`GET` `https://api-testnet.3adao.org/collaterals`

Also retrieves collateral settings such as \
\- MCR: Minimum Collateralization Ratio (%)\
\- MLR: Minimum Liquidation Ratio (%)

### 200: OK JSON Format

```json
[
{
"tokenName": "WMATIC",
"address": "0x0d500b1d8e8ef31e21c99d1db9a6444d3adf1270",
"mcr": 120,
"mlr": 110,
"decimals": 18,
"price": "/collaterals/price/0x0d500b1d8e8ef31e21c99d1db9a6444d3adf1270"
},
{
"tokenName": "USDC",
"address": "0x2791bca1f2de4661ed88a30c99a7a9449aa84174",
"mcr": 110,
"mlr": 105,
"decimals": 6,
"price": "/collaterals/price/0x2791bca1f2de4661ed88a30c99a7a9449aa84174"
},
{
"tokenName": "WETH",
"address": "0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619",
"mcr": 120,
"mlr": 110,
"decimals": 18,
"price": "/collaterals/price/0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619"
}
]
```

## Retrieves collateral price via the core protocol oracles

`GET` `https://api-testnet.3adao.org/collaterals/price/:collateralAddress`

#### Path Parameters

| Name                                                 | Type   | Description              |
| ---------------------------------------------------- | ------ | ------------------------ |
| :collateralAddress\* | String | ERC20 collateral address |

### 200: OK JSON Format

```json
{
"priceInWei": "516830542125875495",
"priceHuman": "0.516830542125875495"
}
```

## Retrieves the full list of core protocol contract ABIs

`GET` `https://api-testnet.3adao.org/abi/list`

### 200: OK JSON Format

```json
[
"/abi/A3A",
"/abi/A3AStaking",
"/abi/AuctionManager",
"/abi/ChainlinkPriceFeed",
"/abi/ConvertedPriceFeed",
"/abi/LastResortLiquidation",
"/abi/LiquidationRouter",
"/abi/MintableToken",
"/abi/MintableTokenOwner",
"/abi/StabilityPool",
"/abi/TokenToPriceFeed",
"/abi/Vault",
"/abi/VaultDeployer",
"/abi/VaultFactory",
"/abi/VaultFactoryHelper"
]
```

## Retrieves a specific ABI of the input contract, along with its deployed address

`GET` `https://api-testnet.3adao.org/abi/`

Example: **`/abi/A3A`**

#### Path Parameters

| Name                                           | Type   | Description     |
| ---------------------------------------------- | ------ | --------------- |
| contractName\* | String | target contract |

### 200: OK JSON Format

```json
{
"address": "0xED6aBF8eb45921E3ec462cD09e9DcDc13b4BA82A",
"abi": [ .... ]
}
```

## Get vaults list and detailed informations

`GET` `https://api-testnet.3adao.org/vaults`

If no vault address is provided, it will return the full list of opened vaults in the protocol.

To get a specific vault details, use **`/vaults/0x....00`**

#### Path Parameters

| Name         | Type   | Description          |
| ------------ | ------ | -------------------- |
| vaultAddress | String | target Vault address |

### 200: OK Full vaults list

```json
[
{
"address": "0x4956538616174ba7b407921AB0Fb0Cce2558EEeF",
"url": "/vaults/0x4956538616174ba7b407921AB0Fb0Cce2558EEeF"
},
{
"address": "0x129AB949Ad24420e840c3de87FA9684BF8A30930",
"url": "/vaults/0x129AB949Ad24420e840c3de87FA9684BF8A30930"
}
]
```

### 200: OK Vault details

```json
{
"address": "0x4956538616174ba7b407921AB0Fb0Cce2558EEeF",
"collaterals": [
"0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270"
],
"vaultName": "MyVault",
"owner": "0x717596024e386BA5c2fb40c3c6DA27e9abD86047",
"debt": "0.0",
"healthFactor": "",
"liquidationFactor": "",
"liquidationThreshold": "46.98459473871595409",
"borrowable": "43.069211843822957916",
"tvl": "51.6830542125875495",
"collateralInfo": [
{
"address": "0x0d500B1d8E8eF31E21C99d1Db9A6444d3ADf1270",
"amount": "100.0",
"price": "0.516830542125875495",
"valueInEur": "51.6830542125875495",
"decimals": 18,
"symbol": "WMATIC",
"isRedeemable": false
}
]
}
```

## Get all vaults that can be redeemed against

`GET` `https://api-testnet.3adao.org/redeemableVaults`

If any vault can be redeemed against, it will also provide which collateral can be redeemed for EURO3

## Get all liquidatable vaults

`GET` `https://api-testnet.3adao.org/liquidatableVaults`

## Get all vaults owned by a specific address

`GET` `https://api-testnet.3adao.org/vaultsByUser/:address`

If no vault address is provided, it will return the full list of opened vaults in the protocol.

To get a specific vault details, use **`/vaults/0x....00`**

#### Path Parameters

| Name     | Type   | Description          |
| -------- | ------ | -------------------- |
| :address | String | target owner address |

### 200: OK Full vaults list

```json
[
{
"address": "0x4956538616174ba7b407921AB0Fb0Cce2558EEeF",
"url": "/vaults/0x4956538616174ba7b407921AB0Fb0Cce2558EEeF"
},
{
"address": "0x129AB949Ad24420e840c3de87FA9684BF8A30930",
"url": "/vaults/0x129AB949Ad24420e840c3de87FA9684BF8A30930"
},
{
"address": "0x28E2dd0a5B54091f47ca379342646A96654A7356",
"url": "/vaults/0x28E2dd0a5B54091f47ca379342646A96654A7356"
},
{
"address": "0x90b3B5f5cefcE34e9B0cBa1A1d8102A3561872D5",
"url": "/vaults/0x90b3B5f5cefcE34e9B0cBa1A1d8102A3561872D5"
}
]
```
