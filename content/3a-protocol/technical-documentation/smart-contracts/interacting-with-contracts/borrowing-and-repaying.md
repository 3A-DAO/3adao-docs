---
title: Borrowing and Repaying
description: How a vault owner borrows EURO3 from a vault and repays the loan.
section: Protocol: Technical
order: 130
---

<!-- archive-notice -->
> **Archived.** The 3A lending protocol and EURO3 on Linea and Polygon were phased out in 2024: no new loans from
> 1 October 2024, and all remaining vaults closed on 30 November 2024
> ([3A DAO's announcement](https://medium.com/@3aDAO/phasing-out-euro3-lending-f5869a3498a8)). This page is kept
> for reference and describes the protocol as it was. Do not send funds to the contracts it lists.

The `vaultOwner()` has the right to borrow from its own vaults, \
provided they have enough collateral to do it.\

Borrow will effectively mint EURO3, thus adding more circulating supply.\
To get `IVault` interface, refer to [Creating a vault](/3a-protocol/technical-documentation/smart-contracts/interacting-with-contracts/creating-a-vault)\

Here's an example of a simple borrowing interaction:

```solidity
import "./IVaultFactory.sol";
import "./IVault.sol";
import "./ERC20.sol";

// --- core contract logic ---
IVaultFactory vaultFactory = IVaultFactory(0x.....0);
address vaultAddress = 0x...0;
address destinationAddress = msg.sender;

IVault myVault = IVault(vaultAddress);

// get the maximum amount you can borrow
(uint256 maxBorrowable, ) = myVault.borrowable();

// borrowing can only be done from the VaultFactory
vaultFactory.borrow(vaultAddress, maxBorrowable, destinationAddress);

// healthFactor is 18 decimals,
// meaning 1e18 = 1.0 HF
uint256 healthFactor = myVault.healthFactor(false);

require(healthFactor > 2 ** 1e18, "borrowed too much!");
```

***

### Repaying your loan

Repaying a loan requires enough EURO3 is approved to be spent by the `VaultFactory`\
Here's an example implementation:

```solidity
import "./IVaultFactory.sol";
import "./IVault.sol";
import "./ERC20.sol";

// --- core contract logic ---
IVaultFactory vaultFactory = IVaultFactory(0x.....0);
address vaultAddress = 0x...0;

IVault myVault = IVault(vaultAddress);

IERC20 euro3 = IERC20(vaultFactory.stable());

uint256 vaultDebt = myVault.debt();
uint256 euro3Balance = euro3.balanceOf(address(this));

euro3.approve(vaultDebt, vaultDebt);

require(euro3Balance >= vaultDebt, "not enough fund to repay fully");

VaultFactory.repay(vaultAddress, vaultDebt);
```
