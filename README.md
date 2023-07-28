# ETH-beginner MY TOKEN
This is a project that has been codoed in solidity programming language. Project creates a custom token with variables and function that perform the basic functionalities of a token such as minting and burning a token values.

## Description

In this solidity smart contract we have used three public variables to store the basic details of the token such as its name, abbriviation and total supply.Mapping is used to map an address with a value. This contract contains two functions mint and burn. Mint function is used to increase the totalSupply of our coin and in contrast burn function is used to destroy token.

## Getting Started

### Executing program
The program is written in solidity programming language and you need either a solidity compiler in your local host or an online IDE to run this code
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

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
    string public tokenname = "Adi money";
    string public tokenAbbrv = "ADM";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address => uint ) public balances;

    // mint function
    function mintToken(address _address, uint _value) public 
    {
        totalSupply = totalSupply + _value;
        balances[_address] += _value;
    }
    // burn function
    function burnToken(address _address, uint _value) public 
    {
        if(balances[_address] >= _value)
        {
        totalSupply = totalSupply - _value;
        balances[_address] -= _value;
        }
        
    }
}

```
To compile the code, if you have set the remix IDE on auto compile mode it will automatically compile the file every few seconds or you can  click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile Assessment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Assessment" contract from the dropdown menu, and then click on the "Deploy" button.

once the contract is deployed, we can check the state variables such as token name, token abbreviations, and total supply.

You can interact with functions by calling the mint function. Click on MyToken contract and select the mint function. Provide address(YOu can copy the same address as the one given in the account block above the deploy button)  and value to the mint function and click on transact to execute the function.

To check to supply of your token click on the public variables totalSupply in the contract section. It will display you the amount of token you minted.

Similarly, you can use the burn function by giving the value and address  and check the value by clicking on the public variable totalSupply. While using burn function we need to bear in mind that the value should not exceed the total supply at any time otherwise the tokens will not burn at all

## Authors

Aditya Bhatt
adityabhatt05101007@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
