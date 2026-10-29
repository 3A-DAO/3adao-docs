---
title: Adding and removing collateral
description: The Vault interface for adding and removing collateral.
section: Protocol: Technical
order: 129
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

### Vault Interface

For ease of understanding and interactions, here's the interface for the current Protocol Vault implementation:

```solidity
//SPDX-License-Identifier: MIT
pragma solidity ^0.8.4;

interface IVault {
    function vaultOwner() external view returns (address);
    function debt() external view returns (uint256);
    function transferVaultOwnership(address _newOwner) external;
    function setName(string memory _name) external;
    function containsCollateral(address _collateral) external view returns (bool);
    function collateralsLength() external view returns (uint256);
    function collateralAt(uint256 _index) external view returns (address);
    function collaterals() external view returns (address[] memory);
    function collateral(address _collateral) external view returns (uint256);
    function factory() external view returns (address);
    function addCollateral(address _collateral, uint256 _amount) external;
    function removeCollateral(address _collateral, uint256 _amount, address _to) external;
    function addBadDebt(uint256 _amount) external;
    function borrowable() external view returns (uint256 _maxBorrowable, uint256 _borrowable);
    function borrow(uint256 _amount) external;
    function repay(uint256 _amount) external;
    function calcRedeem(
        address _collateral,
        uint256 _collateralAmount
    ) external view returns (uint256 _stableAmountNeeded, uint256 _redemptionFee);
    function redeem(
        address _collateral,
        uint256 _collateralAmount
    ) external returns (uint256 _debtRepaid, uint256 _feeCollected);
    function healthFactor(bool _useMlr) external view returns (uint256 _healthFactor);
    function newHealthFactor(uint256 _newDebt, bool _useMlr) external view returns (uint256 _newHealthFactor);
    function borrowableWithDiff(
        address _collateral,
        uint256 _diffAmount,
        bool _isAdd,
        bool _useMlr
    ) external view returns (uint256 _maxBorrowable, uint256 _borrowable);
    function liquidate() external returns (uint256 _forgivenDebt);
}
```

***

### Adding collaterals

In order to borrow EURO3 from the Protocol, you'll need to add some collateral in your vault.\
The [VaultFactory](/3a-protocol/technical-documentation/smart-contracts/interacting-with-contracts/creating-a-vault) provides two methods that lets you do this, depending on the collateral type.\

For example, you may want to add MATIC, without wrapping WMATIC yourself.\
The protocol can do it automatically on your behalf, since we'll treat MATIC as a regular ERC20.

```solidity
import "./IVaultFactory.sol";
// --- core contract logic ---
IVaultFactory vaultFactory = IVaultFactory(0x.....0);
address vaultAddress = vaultFactory.createVault("customName");
uint256 MATIC_AMOUNT = 1e18;
vaultFactory.addCollateralNative(vaultAddress, { value: MATIC_AMOUNT });
```

In case of regular ERC20s the interface looks slightly different and requires an approval step first:

```solidity
import "./IVaultFactory.sol";
import "./IERC20.sol";
// --- core contract logic ---
IVaultFactory vaultFactory = IVaultFactory(0x.....0);

address vaultAddress = vaultFactory.createVault("customName");
uint256 USDC_AMOUNT = 1e18;

IERC20 usdc = IERC20(USDC_ADDRESS);
usdc.approve(vaultAddress, USDC_AMOUNT);

vaultFactory.addCollateral(vaultAddress, address(usdc), USDC_AMOUNT);
```

Vaults are multi-collateral by default, so you'll be able to add different types of collateral in the same `Vault`

***

### Removing collateral

While adding collateral is unrestricted, removing collateral from a vault can only be done by its `vaultOwner()`,\

Removing native collateral, for example MATIC, has its own specific method:

```solidity
import "./IVaultFactory.sol";
import "./IERC20.sol";
// --- core contract logic ---
IVaultFactory vaultFactory = IVaultFactory(0x.....0);

address vaultAddress = vaultFactory.lastVault();
address destinationAddress = msg.sender;

uint256 maticAmount = 1e18;

vaultFactory.removeCollateralNative(vaultAddress, maticAmount, destinationAddress);
```

In case of regular ERC20s the interface looks like the following:

```solidity
import "./IVaultFactory.sol";
import "./IERC20.sol";
// --- core contract logic ---
IVaultFactory vaultFactory = IVaultFactory(0x.....0);

address vaultAddress = vaultFactory.createVault("customName");
uint256 USDC_AMOUNT = 1e18;
address destinationAddress = msg.sender;

IERC20 usdc = IERC20(USDC_ADDRESS);

vaultFactory
    .removeCollateral(vaultAddress,
                        address(usdc),
                        USDC_AMOUNT,
                        destinationAddress);
```

Keep in mind that if you have a debt position opened you can only withdraw up to a target Health Factor of `1.0`
