# ETH-Assessment
This Solidity program is a simple "MyToken" smart contract that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

This contract allows for the creation and management of a simple token on the Ethereum blockchain. It includes functionality to mint new tokens and burn existing tokens, along with storing details about the token.

Requirements
Public Variables: The contract has public variables that store the details about the coin (Token Name, Token Abbrv., Total Supply).
Mapping: There is a mapping of addresses to balances (address => uint).
Mint Function: A function to mint new tokens, increasing the total supply and the balance of the specified address.
Burn Function: A function to burn tokens, decreasing the total supply and the balance of the specified address, with checks to ensure sufficient balance.
Conditional Burn: The burn function includes conditionals to ensure the balance of the "sender" is greater than or equal to the amount to be burned.
Getting Started
Prerequisites
To run this program, you can use Remix, an online Solidity IDE.

Executing Program
Open Remix: Go to the Remix website at Remix Ethereum.

Create a New File: Click on the "+" icon in the left-hand sidebar and save the file with a .sol extension (e.g., MyToken.sol).

Copy and Paste Code: Copy and paste the following code into the file:
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

Compile the Code: Click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Deploy the Contract: Click on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Interact with the Contract: Once the contract is deployed, you can interact with it by calling the mint and burn functions. Click on the "MyToken" contract in the left-hand sidebar to see available functions.
