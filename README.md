# MyToken Smart Contract

## Overview

MyToken is a simple Ethereum smart contract that implements a basic token with functionalities for minting and burning tokens. This contract allows for the creation and destruction of tokens, managing the total supply and individual balances of token holders.

## Features

- **Public Variables**: Store the details about the token, such as its name, abbreviation, and total supply.
- **Balances Mapping**: Maintain a mapping of addresses to their respective token balances.
- **Mint Function**: Increase the total supply and the balance of a specified address.
- **Burn Function**: Decrease the total supply and the balance of a specified address, with checks to ensure sufficient balance.

## Contract Details

### Public Variables

- `tokenName`: The name of the token. (e.g., "META")
- `tokenAbbrv`: The abbreviation of the token. (e.g., "MTA")
- `totalSupply`: The total number of tokens in existence. Initially set to 0.

### Mapping

- `balances`: A mapping from addresses to their token balances.

### Mint Function

The `mint` function allows the creation of new tokens.

**Syntax**:
```solidity
function mint(address _address, uint _value) public;
```

**Parameters**:
- `_address`: The address to which the tokens will be minted.
- `_value`: The amount of tokens to mint.

**Functionality**:
- Increases `totalSupply` by `_value`.
- Increases the balance of `_address` by `_value`.

### Burn Function

The `burn` function allows the destruction of tokens.

**Syntax**:
```solidity
function burn(address _address, uint _value) public;
```

**Parameters**:
- `_address`: The address from which the tokens will be burned.
- `_value`: The amount of tokens to burn.

**Functionality**:
- Decreases `totalSupply` by `_value`.
- Decreases the balance of `_address` by `_value` if `_address` has sufficient balance.

## Example

Here is an example of how to interact with the MyToken contract:

```solidity
// Deploy the contract
MyToken token = new MyToken();

// Mint 100 tokens to an address
token.mint(0x123..., 100);

// Check the total supply
uint supply = token.totalSupply(); // 100

// Check the balance of the address
uint balance = token.balances(0x123...); // 100

// Burn 50 tokens from the address
token.burn(0x123..., 50);

// Check the total supply
supply = token.totalSupply(); // 50

// Check the balance of the address
balance = token.balances(0x123...); // 50
```
