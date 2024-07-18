# BLSStaking Smart Contract

The **BLSStaking**  smart contract is designed to facilitate the staking and unstaking of BLS tokens in exchange for staked BLS tokens (stBLS). This contract allows users to stake their BLS tokens and receive stBLS tokens, representing their stake, which can be used for various decentralized finance (DeFi) applications. Users can also unstake their BLS tokens by burning their stBLS tokens.

## Features

- **Staking**: Users can stake a specified amount of BLS tokens, which are transferred from their account to the contract. In return, an equivalent amount of stBLS tokens is minted and credited to the user.
  
- **Unstaking**: Users can unstake a specified amount of stBLS tokens, which are burned from their account. The equivalent amount of BLS tokens is then transferred back to the user from the contract.

## Functionality

- **Ownership**: The contract inherits from Ownable, allowing the owner to perform administrative functions.
  
- **Token Management**: The contract uses two ERC20 token interfaces (`IERC20`): `blsToken` for the BLS token and `stBlsToken` for the stBLS token. The addresses for these tokens are set using the `setAddresses` function.
  
- **Mapping**: `stakedAmountOf` keeps track of the amount of BLS tokens staked by each user.

## Usage

1. **Deployment**: Deploy the contract with an initial owner.
  
2. **Configuration**: Set the addresses of the BLS and stBLS tokens using the `setAddresses` function.
  
3. **Staking**: Users stake BLS tokens to receive stBLS tokens in return.
  
4. **Unstaking**: Users can unstake stBLS tokens to retrieve their originally staked BLS tokens.

## Security

- **Require Statements**: Includes checks to ensure that users cannot stake or unstake zero tokens and that users cannot unstake more tokens than they have staked.
  
- **Token Transfers**: Utilizes safe transfer methods (`transferFrom`, `transfer`) to prevent token loss and ensure correct handling of token balances.

## Contract Owner

- The owner has administrative rights to manage the contract, including setting token addresses.

## Notes

- This contract assumes the presence and functionality of the `IERC20` interface for both BLS and stBLS tokens.
