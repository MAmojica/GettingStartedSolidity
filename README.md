MyToken Contract
Overview
MyToken is a simple Ethereum smart contract that implements a basic token with minting and burning functionalities. This contract allows for the creation and destruction of tokens, managing the total supply and individual balances of token holders.

Requirements
The contract satisfies the following requirements:

Public Variables:

tokenName (Token Name)
tokenAbbrv (Token Abbreviation)
totalSupply (Total Supply)
Mapping:

A mapping of addresses to balances (mapping(address => uint) public balances)
Mint Function:

Increases the total supply and the balance of a specified address.
Burn Function:

Decreases the total supply and the balance of a specified address.
Ensures the balance of the address is greater than or equal to the burn amount.
Public Variables
string public tokenName = "META";
The name of the token.
string public tokenAbbrv = "MTA";
The abbreviation of the token.
uint public totalSupply = 0;
The total supply of tokens in existence.
Mapping
mapping(address => uint) public balances;
A mapping from addresses to their respective balances.
Functions
Mint Function
solidity
Copy code
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
Parameters:
_address: The address to which the tokens will be minted.
_value: The amount of tokens to mint.
Functionality:
Increases the total supply by the _value.
Increases the balance of _address by the _value.
Burn Function
solidity
Copy code
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
Parameters:
_address: The address from which the tokens will be burned.
_value: The amount of tokens to burn.
Functionality:
Decreases the total supply by the _value.
Decreases the balance of _address by the _value if _address has sufficient balance.
