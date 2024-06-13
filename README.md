# ETH_begnr_MetaC
It is a project in which i have created a smart contract used for minting and burning a specific token. This code helps Beginners to understand the basic concept of minting a token and how are they used in real life blockchain.

## Description

In this program , every basic concept of solidity has been used , and has been implemented using functions. It is a best program for someone who is looking for a basic code which performs minting and burning operations in a smart contract.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Assessment.sol). Copy and paste the following code into the file:

    // SPDX-License-Identifier: UNLICENSED
    pragma solidity 0.8.18;

    /*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply).
    2. Your contract will have a mapping of addresses to balances (address => uint).
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount.
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
    */
    contract MyToken {
    
    // public variables here

    string public tName = "Juicy Dollar";
    string public tAbbr = "JD";
    uint public totalSupply = 0;

    // mapping variable here

    mapping(address => uint) public balances;

    // mint function

    function minting (address _add , uint _val) public 
    {
        totalSupply +=  _val;
        balances[_add] +=  _val;
    }

    // burn function

    function burning (address _add , uint _val) public 
    {
        if(balances[_add] >= _val)
        {
        totalSupply -= _val;

        balances[_add] -= _val;
        }
    }
    }

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile Assessment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the minting and burning function, which requires an address as a one of the parameter and the amount you want to mint or burn as the other parameter. Once you have filled the values, the totalsupply value will be increamented or decreamented as per the called function. and the changes will be reflected in the balance of the provided address.

## Authors

Jatin Dhakar 

## License

This project is Unlicensed
