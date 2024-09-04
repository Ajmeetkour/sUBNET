# AVAX-ADVANCE-Module1 DeFi Empire Clone
## Description
The project includes two smart contracts, ERC20 and GameATM, designed to enable a decentralized gaming ecosystem on the Avalanche blockchain. Players can explore, make purchases, and engage in battles using digital assets while earning rewards in custom tokens. Players receive choice boards based on their badges, which they can also transfer to friends within the game.

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
   
## ERC20GameContract.sol
The GameToken contract is an ERC20-like token contract with basic functionalities such as transferring tokens, approving allowances, and minting or burning tokens. Key features include:
### Token Management
The contract handles the total token supply, tracks the balances of each account, and manages allowances for delegated transfers.
Transfers
Users can send tokens to other addresses or authorize third parties to transfer tokens on their behalf through allowances.
Minting and Burning
The contract enables the creation of new tokens, adding them to the caller's account, and the destruction of tokens from the caller's balance.

## SecureVault.sol
The SecureVault contract functions as a vault, overseeing player interactions within the game while using GameToken as the primary currency. Its key features include:

### Player Management
Keeps track of players through a Gamer struct, storing details such as token balance, experience points, achievements, battle victories, explorations, voting rights, player level, and name.
Token Operations

Players can deposit (addTokens) or withdraw (removeTokens) tokens from the vault, with their balances being updated accordingly.
Game Interactions

Battles and Exploration: Players can challenge other players in battles (engageBattle) or undertake exploration missions (embarkExplore), earning rewards and experience points.
Purchasing Items: Players can use tokens to buy in-game items (buyItem).
Token Transfer: Allows players to transfer their in-game tokens to other players (transferTokens).
Leaderboard and Achievements

Leaderboard: Tracks a leaderboard ranked by players' token balances and battle wins (getLeaderboard).
Achievements and Rewards: Players can earn additional tokens and rewards based on their achievements and participation (rewardAchievements, awardTokenBonus).
Player Governance and Moderation

Voting Rights: Players can acquire voting rights after accumulating enough experience points.
Player Data Management: Supports adding new players (addPlayer), simulating battles and explorations for testing, and managing player data.

Author:
Ajmeet kour

License
This project is licensed under the MIT License  
