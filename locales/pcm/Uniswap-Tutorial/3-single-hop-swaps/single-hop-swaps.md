Na single hop swaps dey allow yusers exchange one token for di other directly within a liquidity pool. For dis section we wan learn how to use di Uniswap V3 Swap contract to execute single-hop swaps.

## Di function parameters

For line 8, we define a function called `swapExactInputSingleHop`. Dis function executes a single-hop swap. E fit take di following parameters:

- **`address tokenIn`**: di address of di token don send.
- **`address tokenIn`**: di address of di token don send.
- **`uint24 poolFee`**: di fee associated with the swap.
- **`uint amountIn`**: di amount of di input token being sent.

E returns a `uint` called `amountOut`, which is the amount of the output token that was received.

## Dis na Function Body

Di function body we fit first transfer di input token from the sender to our contract, line 14.
We fit approve di uniswap swap contract to spend di input token on our behalf, line 15.

For liine 17, we fit create im instance for di `ExactInputSingleParams` struct. Dis struct contain di parameters wey require for di `exactInputSingle` function on line 45, which will execute the single-hop swap. We repeat ISwapRouter.ExactInputSingleParams\` two times on di line because we are making an instance of a struct that is defined in an interface.

## Di Parameters of di ExactInputSingleParams Struct

We fit set di parameters of di struct as follows:

- **`tokenIn`**: We fit set dis to di `tokenIn` parameter of our function.
- **`tokenIn`**: We fit set dis to di `tokenIn` parameter of our function.
- **`path`**: We don set dis to the `path` parameter of our function.
- **`recipient`**: We set this to the sender of the transaction.
- **`deadline`**: nwe go set di current timestamp. We dey do dis becuz say we want transaction mey dem processed am.
- \*`amountIn`\*\*: We set am go di `amountIn` parameter of our function.
- **`amountOutMinimum`**: We don set dis one to 0 becuz say we no wan specify im minimum amount of di output token wey dey willing to accept.
- **`sqrtPriceLimitX96`**: Wedon set dis to 0 becuz we no wan want to specify a limit on the price.

## Dis na Executing the Single-hop Swap

For line 29, we fit assign di output of di `exactInputSingle` function to the `amountOut` variable. Dis function dey remove di single-hop swap and returns di amount of di output token dat was received.