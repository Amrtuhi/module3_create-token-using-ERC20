# Creating and mint token using ERC20 contract

This Solidity program is a simple "Minting" tokena and transfer fungible token from one account to another and also can perform different operations like burn burn from and etc.This uses the mint syntax and knowledge of solidity programming.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. This contract is made using ERC20 for creating a fungible account .It also uses hardhat ad openZeppelins these are the tools for managing and eveloping our smart contract. This program is used to mint ,burn,and burnfrom a specific account and perform many other different tasks.

## Getting Started

### Executing program

->to run this contact use remix ethereum IDE.
->need hardhat(import in the IDE ).
->need openzepplins(install openzepplins).
->write the smart contract .
->write different functions to perform different tasks and perform all tasks like mint,burn etc.
->compiler the smart contract by checking whether the version is smart written on both smart contract and compiler.
->deply the smart contrcat.

```smart contract
// SPDX-License-Identifier: MIT
// Compatible with OpenZeppelin Contracts ^5.0.0
pragma solidity ^0.8.20;

import "hardhat/console.sol";
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol"; // for Burn
import "@openzeppelin/contracts/access/Ownable.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Permit.sol";

contract MyToken is ERC20, ERC20Burnable, Ownable, ERC20Permit {
    constructor(address initialOwner)
        ERC20("MyToken", "TK")
        Ownable(initialOwner)
        ERC20Permit("MyToken")
    {}

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function burn(uint256 amount) public override {
        _burn(_msgSender(), amount);
    }

    
}

```

## Authors

Amrita kumari  
https://www.linkedin.com/in/amrita-kumari-753319232/


## License

This project is licensed under the MIT License .
