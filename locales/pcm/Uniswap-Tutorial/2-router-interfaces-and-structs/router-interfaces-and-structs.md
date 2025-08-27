Di entire UniswapSwapExample kontract go only dey present for section 5 for dis tutorial.  Before then, we dey build up blocks of code.

Dis section dey explore di 'ISwapRouter' interface, which defines di fuktions wey fit call for di Uniswap Swap kontract.

Single-hop swaps dey allow users exchange on tokin for anoda directli wey dey liquidity pool.
Muiti-hop swaps dey allow users exchange one tokin for anoda by routing through multiple Tokins.

Interface dey Solidity specifi fuktions wey gats dey for di kontract wey inherits Dem.  Dem dey useful for declaring wetin fuktions be dey support and allow for easier integration and interaction between different kontracts.

Structs dey use to defines kustom data types.

## ISwapRouter Interface

The ISwapRouter interface defines the functions that can be called on the Uniswap Swap contract. We will need to use this interface to interact with the Uniswap Swap contract and execute swaps.

On line 5, we define a constant variable called `router` that is of type `ISwapRouter`. We set the value of this variable to the interface instance of a smart contract that is deployed at the address `0xE592427A0AEce92De3Edee1F18E0157C05861564`. This is the address of the Uniswap V3 Swap contract on the Ethereum mainnet.

On line 9, we define an interface called `ISwapRouter`. This interface defines two functions: `exactInputSingle` and `exactInput`.

## exactInputSingle

On line 25, we define a struct called `ExactInputSingleParams`. This struct defines the parameters that are required for our exactInputSingle function on line 21, which will execute a single-hop swap. The struct has the following parameters:

- **`address tokenIn`**: The address of the token being sent.
- **`address tokenOut`**: The address of the token being received.
- **`uint24 fee`**: The fee associated with the swap.
- **`address recipient`**: The address that will receive the output token.
- **`uint deadline`**: A timestamp by which the transaction must be processed, for time-limiting the swap.
- **`uint amountIn`**: The amount of the input token being sent.
- **`uint amountOutMinimum`**: The minimum amount of the output token that the sender is willing to accept, to protect against unfavorable price movements.
- **`uint160 sqrtPriceLimitX96`**: A limit on the price, represented in a specific format, to prevent the swap from occurring at unfavorable prices.

## exactInput

On line 25, we define a struct called `ExactInputParams`. This struct defines the parameters that are required for our `exactInput` function on line 33. This function will execute a multi-hop swap. The struct has the following parameters:

- **`bytes path`**: Encoded information about the swap path (i.e., which tokens to swap through).
- **`address recipient`**: The address receiving the output tokens.
- **`uint deadline`**: Similar to above, a timestamp by which the transaction must be processed.
- **`uint amountIn`**: The amount of the input token.
- **`uint amountOutMinimum`**: The minimum amount of the output token the sender expects to receive.

