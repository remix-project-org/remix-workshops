For dis area we do dive into di `swapExactInputMultiHop` function in the `UniswapV3SwapExamples` contract. Dis function allow more complex token swaps by allowing yuser to fit specify a custom path through multiple liquidity pools.

Yuser want swap token A for token D, but they dem no direct liquidity pool for A and D, di yuser fit specify im path through multiple tokens. Di yuser fit swap A for B, then B for C, and finally C for D. ids of course automatically done by di un9swap V3 swap contract.

### Di Parameters and Return Value

For line 32, we define function called `swapExactInputMultiHop`. Dis kind function dey remove multi-hop swap. E go take di ff parameters:

- **`bytes calldata path`**: Encoded information about di swap path (i.e., which tokens to swap through).
- **`address tokenIn`**: di address of di token ddem don send am.
- **`uint amountIn`**: di amount of di input token being sent.

E dey return im unit called `amountOut`, which e dey amount of the output token that was received.

### Dis Function Body

For di function body we go first transfer di input token from di sender go our contract line 38.
We go approve im uniswap swap router to fit spend di input token on our behalf, line 41.

For di line 43, we fit create an instance of the `ExactInputParams` struct, line 73. Dis struct e contain im parameters wey dey required for our exactInput\` function on line 81, which will execute the multi-hop swap.

We don set di parameters like dis:

- **`path`**: We don set dis to the `path` parameter of our function.
- **`recipient`**: We set this to the sender of the transaction.
- **`deadline`**: We set this to the current timestamp. We dey do dis becuz say we want transaction mey dem processed am.
- \*`amountIn`\*\*: We set am go di `amountIn` parameter of our function.
- **`amountOutMinimum`**: We don set dis one to 0 becuz say we no wan specify im minimum amount of di output token wey dey willing to accept.

For line 53 we execute the multi-hop swap by calling the `exactInput` function. Dis function dey return im amount of di output token wey we received.