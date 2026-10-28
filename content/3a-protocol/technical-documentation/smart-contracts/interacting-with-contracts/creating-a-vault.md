---
title: Creating a vault
description: How to create a vault through the VaultFactory contract.
section: Protocol: Technical
order: 128
---

The majority of user-facing operation for the Protocol revolves around the `VaultFactory`, which address can be retrieved by using the [API](/3a-protocol/technical-documentation/smart-contracts/api) along with its ABI\

Solidity interface for `VaultFactory` is:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.4;

interface IVaultFactory {
    event NewVault(address indexed vault, string name, address indexed owner);
    event PriceFeedUpdated(address indexed priceFeed);

    function setPriceFeed(address _priceFeed) external;
    function vaultCount() external view returns (uint256);
    function lastVault() external view returns (address);
    function firstVault() external view returns (address);
    function nextVault(address _vault) external view returns (address);
    function prevVault(address _vault) external view returns (address);
    function liquidationRouter() external view returns (address);
    function MAX_TOKENS_PER_VAULT() external view returns (uint256);
    function priceFeed() external view returns (address);
    function transferVaultOwnership(address _vault, address _newOwner) external;
    function createVault(string memory _name) external returns (address);
    function addCollateralNative(address _vault) external payable;
    function removeCollateralNative(address _vault, uint256 _amount, address _to) external;
    function addCollateral(address _vault, address _collateral, uint256 _amount) external;
    function removeCollateral(address _vault, address _collateral, uint256 _amount, address _to) external;
    function borrow(address _vault, uint256 _amount, address _to) external;
    function distributeBadDebt(address _vault, uint256 _amount) external;
    function closeVault(address _vault) external;
    function repay(address _vault, uint256 _amount) external;
    function redeem(address _vault, address _collateral, uint256 _collateralAmount, address _to) external;
    function liquidate(address _vault) external;
    function isLiquidatable(address _vault) external view returns (bool);
    function isReedemable(address _vault, address _collateral) external view returns (bool);
    function containsVault(address _vault) external view returns (bool);
    function stable() external view returns (address);
    function isCollateralSupported(address _collateral) external view returns (bool);
}
```

Creating in solidity is as simple as the following:

```solidity
import "./IVaultFactory.sol";
// --- core contract logic ---
IVaultFactory vaultFactory = IVaultFactory(0x.....0);
address vaultAddress = vaultFactory.createVault("customName");
```
