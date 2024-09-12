# AVAX-ADVANCE-Module1 1 DeFi Empire Clone
## Description
This project includes several smart contracts:

1. __ERC20:__ Implements the ERC20 token standard with minting, burning, and transferring capabilities.
2. __Vault:__ Acts as an in-game bank where players can deposit and withdraw tokens.
3. __Marketplacehub:__ In this we can postoffers, removeoffers, and purchaseoffers.

## EVM Subnet Configuration - Step by Step Guide
Here's a overview of the steps you need to take:

 #### 1. Set up your EVM subnet:
   you can use our guide and the Avalanche documentation to create a custom EVM subnet on the Avalanche network.

#### 2. Define your native currency:
   You can set up your own native currency, which can be used as the in-game currency for your DeFi Kingdom clone.

#### 3. Connect to Metamask: 
  Connect you EVM Subnet to metamask, this can be done by following the steps laid out in our guide.

#### 4. Deploy basic building blocks:
  You can use Solidity and Remix to deploy the basic building blocks of your game, such as smart contracts for battling, exploring, and trading. These contracts will define the game rules, such as liquidity pools, tokens, and more.
   

## Functionality
#### ERC20 Contract
* Minting: mint(uint amount)
* Burning: burn(uint amount)
* Transferring: transfer(address recipient, uint amount)
* Approval: approve(address spender, uint amount)
* TransferFrom: transferFrom(address sender, address recipient, uint amount)
#### Vault Contract
* Deposit: deposit(uint amount)
* Withdraw: withdraw(uint shares)
#### MarketplaceHub Contract
* postoffer: postoffer(address _item, uint256 _cost)
* purchase: purchase(uint256 _offerId)
* getoffer: getOffer(uint256 _offerId) external view returns (Offer memory)
* removeoffer: removeOffer(uint256 _offerId)


## Working
1. __Deploy ERC20 Contract:__ Compile and deploy the ERC20 contract first. Copy the contract address.

2. __Deploy Vault Contract:__ Use the ERC20 contract address as a parameter for the Vault contract constructor.

3. __Deploy Other Contracts:__ Deploy the MarketplaceHub contract.

4. __Interact with Contracts:__ Use Remix IDE or any compatible interface to interact with the deployed contracts.



## Author:
Ajmeet kour

## License
This project is licensed under the MIT License  
