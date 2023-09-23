## Introduction of Repository 

This repository contains a Solidity smart contract named MyToken for a custom token called "Code" with the symbol "Super Code." This README file provides an overview of the project, code explanation, deployment instructions, usage guidelines, and the advantages of using this token contract.

## Introduction To Token Contract 

The Tokening contract serves as a basic example of a token contract on the Ethereum blockchain. It includes functionalities for minting (creating) and burning (destroying) tokens. This contract can be a foundation for building more complex token-based applications or for learning purposes.

## Code Explanations

Variables tokenName and tokenSymbol define the name and symbol of the token. totalSupply tracks the total supply of tokens. balances is a mapping that keeps track of token balances for each address. Mint Function mint allows the creation of new tokens and assigns them to a specified address. It requires a valid recipient address and increases the total supply. Burn Function burn allows an address to burn (destroy) their tokens. It requires that the sender has enough tokens to burn, and it decreases the total supply.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract Tokening {

    string public tokenName="Welcome";
    string public tokenSymbol="Program";
    uint256 public totalSupply=0;

    mapping(address => uint256) public balances;

    function mint(address _to, uint256 _value) external {
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(uint256 _value) external {
        require(balances[msg.sender] >= _value, "No balance");
        totalSupply -= _value;
        balances[msg.sender] -= _value;
    }

}
```

- The SPDX-License-Identifier specifies the license for the code (MIT License in this case).
- pragma solidity ^0.8.0; indicates that the contract is written in Solidity version 0.8.0 or a compatible version.
- MyToken is the name of the Solidity contract.
- tokenName and tokenSymbol represent the name and symbol of the token, respectively.
- totalSupply stores the total number of tokens issued, initialized to 0.
- balances is a mapping that associates Ethereum addresses (users) with their token balances.
- mint is an external function that allows the creation of new tokens and assigns them to a specified address.
-It requires a valid _to address (not the zero address) and an _value representing the number of tokens to mint.
-It increases the totalSupply by _value and adds _value to the balance of the recipient address.
- burn is an external function that allows an address to burn (destroy) their own tokens.
-It requires that the sender has a balance of tokens greater than or equal to _value.
-It decreases the totalSupply by _value and deducts _value from the sender's balance.

This Tokening contract is a basic example of a token contract, demonstrating concepts like token creation, transfer, and burning. It can be extended and customized for specific use cases, such as creating your own tokens or integrating into decentralized applications. Make sure to deploy and interact with it on the Ethereum blockchain using appropriate development tools and networks.

## Testing the Token Contract

**Mint Function:**
  To test the mint function, follow these steps:
  Copy your account address.
  Enter a value (e.g., 1000) in the _value field.
  Click the "Transaction" button.

Look for another green checkmark, indicating a successful transaction.
Confirm if the totalSupply variable has increased to verify the token minting.

**Burn Function:**

  To test the burn function, follow these steps:
  Enter a value (e.g., 50) in the _value field.
  Click the "Transaction" button.
  Verify that the totalSupply has been reduced to reflect the token burning.

Congratulations! You've successfully deployed and tested the "Tokening" Ethereum smart contract. This contract provides a basic framework for creating and managing tokens on the Ethereum blockchain. You can further customize and integrate it into your projects as needed.
