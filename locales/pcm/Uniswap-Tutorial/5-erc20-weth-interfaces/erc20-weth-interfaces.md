Dis area we go explore di `IERC20` interface, na standard interface for talking with ERC-20 tokens and di `IWETH` interface, a standard interface for interacting with wrapped Ether (WETH). To fit understand dis interfacee dey crucialas e dey use di uniswap V3 swap contract to fit handle token transfers and approval.

U fit find solidity ERC20 token course for beginners in learnEth to understand di ERC20 token standard in more detail.

## Na IERC20 Interface

On line 80, we fit define di `IERC20` interface. Dis interface defines a standard set of function dat ERC-20 tokens must implement. Make we chack di key function within dis interface:

### na 1. dis na totalSupply

For dis line 81 we define di `totalSupply` function. Di function return di total supply of di token.

### 2. balanceOf

On line 83, we define the `balanceOf` function. This function returns the balance of the specified address.

### 3. transfer

On line 85, we define the `transfer` function. This function transfers tokens from the sender to the specified recipient.

### 4. allowance

On line 87, we define the `allowance` function. This function returns the amount of tokens that the spender is allowed to spend on behalf of the owner.

### 5. approve

On line 89, we define the `approve` function. When called, this function approves a spender to spend the specified amount of tokens on behalf of the sender.

### 6. transferFrom

On line 91, we define the `transferFrom` function. This function transfers tokens from the specified sender to the recipient. The function can only be called by the spender if the spender is allowed to spend the specified amount of tokens on behalf of the sender.

### 7. Events

On lines 102-103, we define the `Transfer` and `Approval` events. These events are emitted when the `transfer` and `approve` functions are called, respectively.

## IWETH Interface

On line 106, we define the `IWETH` interface. This interface extends the `IERC20` interface and defines two additional functions:

### 1. deposit

On line 107, we define the `deposit` function. This function deposits ETH into the contract and returns the equivalent amount of WETH. This function is used to wrap ETH into WETH.
We need to wrap ETH into WETH because the Uniswap V3 Swap contract only supports ERC-20 tokens.

### 2. withdraw

On line 109, we define the `withdraw` function. This function withdraws the specified amount of WETH from the contract and returns the equivalent amount of ETH. This function is used to unwrap WETH into ETH.

## Conclusion

In this tutorial, we explored the Uniswap V3 Swap contract.  To get a full sense of how Uniswap works, try making some swaps on the <a href="https://app.uniswap.org/" target="_blank">Uniswap DApp</a> and go to the <a href="https://docs.uniswap.org/" target="_blank">Uniswap docs</a>.
