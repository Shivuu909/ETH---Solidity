
# Project Title

MyToken ERC-20 Compatible Smart Contract

## Description

The MyToken smart contract is built using Solidity and allows for the creation and management of a custom token. It includes features such as public variables for token details, a mapping for address balances, and functions to mint and burn tokens. The mint function increases the total supply and the balance of a specified address, while the burn function decreases them, ensuring that an address cannot burn more tokens than it holds.

## Getting Started

### Installing

To use this smart contract, follow these steps in Remix IDE:

1. Open Remix IDE: Go to Remix IDE.

2. Create a New File: In the Remix file explorer, create a new file named MyToken.sol.

3. Copy the Contract Code: Copy and paste the following code into MyToken.sol:

### Executing program

Compile the Contract:

Select the Solidity compiler version 0.8.18.
Click on the Solidity Compiler tab in Remix and hit the Compile MyToken.sol button.
Deploy the Contract:

Go to the Deploy & Run Transactions tab.
Select Injected Web3 as the environment to deploy to a testnet or JavaScript VM for local testing.
Click the Deploy button for MyToken.

Interact with the Contract:

-After deployment, you can interact with the contract using the deployed contract's interface in Remix.
-To mint tokens, call the mint function with an address and a value.
-To burn tokens, call the burn function with an address and a value.
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
  string public tokenname = "META";
  string public tokenAbbrv = "TA";
  uint public Totalsupply = 0;
    // mapping variable here
  mapping(address => uint) public balances;
    // mint function
function mint (address _address_, uint _value_) public {
  Totalsupply += _value_;
  balances[_address_] += _value_;
}
    // burn function
function burn (address _address_, uint _value_) public {
  if(balances[_address_] >= _value_){
  Totalsupply -= _value_;
  balances[_address_] -= _value_;
  }
}
}

```

## Help

For common issues:

Compilation Errors: Ensure you are using Solidity version 0.8.18.
Deployment Issues: Check your Remix IDE environment and the network configuration.

For additional help, refer to the Remix IDE documentation and resources.

## Authors

Shivansh Chandra 
https://github.com/Shivuu909


