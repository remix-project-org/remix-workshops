Dis area we go explore di `IERC20` interface, na standard interface for talking with ERC-20 tokens and di `IWETH` interface, a standard interface for interacting with wrapped Ether (WETH). To fit understand dis interfacee dey crucialas e dey use di uniswap V3 swap contract to fit handle token transfers and approval.

U fit find solidity ERC20 token course for beginners in learnEth to understand di ERC20 token standard in more detail.

## Na IERC20 Interface

On line 80, we fit define di `IERC20` interface. Dis interface defines a standard set of function dat ERC-20 tokens must implement. Make we chack di key function within dis interface:

### na 1. dis na totalSupply

For dis line 81 we define di `totalSupply` function. Di function return di total supply of di token.

### na 2. di balance of

For dis line 83 we talk di `balanceOf` function. Dis function return di balance of di specified address.

### 3. di tansfer

For dis line 85 we talk di `balanceOf` function. Dis function dey transfer tokens from im sender go di specified recipient.

### 4. dis na allowance

Di line 87 define im allowance function. Dis function dey return im amount of token wey di spender allow spend on im behalf of di owner.

### dis na 5. approve am

For line 89 define the `approve` function. When di function approve im spender to spend di specified amount of im token on behalf of di sender.

### na 6. dis na transferFrom

For line 91 e define the `transferFrom` function. Dis function transfer token from di specified sender go di recipient. Di function fit call di spender if di spender allow to spend di specified amount of im token on im behalf.

### dis na 7. Im event

For line 102-103, we fit define di `Transfer` and `Approval` events. Dis event dey comot when di transfer and `approve` functions are called, respectively.

## Dis na IWETH Interface

Di line 106, we define di `IWETH` interface. Dis interface di extend di `IERC20` interface and defines two additional functions:

### 1. dem deposit

For line 107, we define di `deposit` function. Dis function deposits ETH for im contract and return di equivalent amount of WETH. Dis function dey used wrap ETH into WETH.
We need to wrap ETH into WETH becuz di Uniswap V3 swap contract only di support ERC-20 tokens.

### 2. dis na withdraw

For di line 109, we define di `withdraw` function. Dis function withdraws di specified amount of WETH from di contract and returns the equivalent amount of ETH. Dis function dey use unwrap WETH into ETH.

## Dis Conclusion

Di tutorial we explored di Uniswap V3 Swap contract.  To fit get full sense of how di uniswap works, try make some swaps for di <a href="https://app.uniswap.org/" target="_blank">Uniswap DApp</a> and go to the <a href="https://docs.uniswap.org/" target="_blank">Uniswap docs</a>.
