# Bonding Curve Module

## Overview
This Move module implements a simple bonding curve mechanism for buying tokens. A bonding curve is a mathematical curve that defines the price of a token based on its supply. As more tokens are purchased, the price increases linearly.

## Features
- **Initialization**: Allows an owner to set up the bonding curve with a base price.
- **Token Purchase**: Buyers can purchase tokens, and the price increases as more tokens are bought.
- **Fund Transfer**: The module ensures that buyers pay the appropriate cost in AptosCoin, which is transferred to the seller.

## Module Structure

### Structs
- `BondingCurve`: Stores the total supply of tokens and the base price.

### Functions
- `initialize(owner: &signer, base_price: u64)`: Initializes a bonding curve contract with a base price.
- `buy_tokens(buyer: &signer, seller: address, amount: u64)`: Allows a buyer to purchase tokens, transferring the corresponding AptosCoin to the seller.

## Usage

### Deploying the Module
1. Compile the Move module.
2. Deploy it to the Aptos blockchain.
3. Call `initialize` with the desired base price.

### Buying Tokens
1. A buyer calls `buy_tokens` with the amount they wish to purchase.
2. The cost is calculated as `base_price + total_supply` per token.
3. The required AptosCoin is transferred from the buyer to the seller.
4. The total supply of tokens increases.

## Example
```move
// Initialize the bonding curve with a base price of 10
MyModule::BondingCurve::initialize(&owner, 10);

// Buyer purchases 5 tokens from the seller
MyModule::BondingCurve::buy_tokens(&buyer, seller_address, 5);
```

## License
This project is licensed under the MIT License.

## Contrat Address
0xc7347f50979fdd3815a4dc0ee6fe4f201f701d2ca531ae0a5ddf04b10fe73cc1
