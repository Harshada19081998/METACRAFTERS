## MY TOKEN.SOL
This is a Solidity smart contract for a token called "MyToken". 

## DESCIRPTION
This program is a contract written in Solidity, a language used for developing smart contracts on the Ethereum blockchain.
The code is a Solidity smart contract for a basic token called "MyToken". It also has two public variables for the token name and abbreviation, and a total supply variable. It has a mapping variable called "balances" which maps addresses to their token balances.
This contract has two functions called "mint" and "burn". The "mint" function  adds the given value to the balance of the specified address. The "burn" function  reduces the balance of the specified address by the given value,only if the address has sufficient balance.

## GETTING STARTED
Using remixIDE to compile and run and deploy the program.

## EXECUTING THE PROGRAM
* Create a new folder named my token.Sol
* A new tab will open 
* Write the contract in solidity 
* If the remix is on auto compile and run,the written code will be compiled and run automatically but if it is not on auto compile then we have to manually compile and   run the code by selecting the option as compile and run in the left menu
* After compiling we deploy the contract.
 Then if the code is deployed successfully we can check the token name and token abbreviation we have given in the code 
* By clicking on tokenabbvr we can check the token abbreviation and similarly we can check token supply and tokrn name tooo.
 (firstly we will have 0 balance in our account) 
* For minting we click on min button then we paste the account address (we have provided after deploying the contract) then we put value ofnhow much token we have to     mint suppose lets take 100 tokens then click transact.(tokens will be transacted in the account)
* To check thr balance click on  balances then paste account address then click on call we will get the account balance
* Then to burn some tokens we will click on burn and then paste account address then set the value to 70 (70 tokens will be burnt from our account)
* To check balance again press on call we will get the latest balance. 100-70=30 (30 will be the latest balance).
* This is all for this contract.


## CONTRACT 

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


contract MyToken {

    // public variables here
   string public tokenName ="WEB3";
   string public tokenAbbvr= "WEB";
   uint public totalSupply=0;
    // mapping variable here
   mapping(address=> uint) public balances;
    // mint function

   function mint (address _address, uint _value) public {
    totalSupply +=_value;
    balances[_address] += _value;
   }
    // burn function
   function burn (address _address,uint _value) public {
       if(balances[_address]>=_value)
       {
         totalSupply -=_value;
         balances[_address] -= _value;
       }
    
   }
}
