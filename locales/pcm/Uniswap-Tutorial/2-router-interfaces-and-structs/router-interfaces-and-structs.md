Di entire UniswapSwapExample kontract go only dey present for section 5 for dis tutorial.  Before then, we dey build up blocks of code.

Dis section dey explore di 'ISwapRouter' interface, which defines di fuktions wey fit call for di Uniswap Swap kontract.

Single-hop swaps dey allow users exchange on tokin for anoda directli wey dey liquidity pool.
Muiti-hop swaps dey allow users exchange one tokin for anoda by routing through multiple Tokins.

Interface dey Solidity specifi fuktions wey gats dey for di kontract wey inherits Dem.  Dem dey useful for declaring wetin fuktions be dey support and allow for easier integration and interaction between different kontracts.

Structs dey use to defines kustom data types.

## ISwapRouter Interface

Di ISwapRouter interface defines di fuktions wey dem dey call for di Uniswap Swap kontract. We go need use dis interface to interact with di Uniswap Swap kontract and comot di swaps.

For line 5, we defines kontract variable called 'router' dat na for type 'ISwapRouter'. We set di value for dis variable to di interface instance of smart kontract wey dem deploy for di address '0xE592427A0AEce92De3Edee1F18E0157C05861564'. Dis na di address for di Uniswap V3 Swap kontract on di Ethereum Mainnet.

For line 9, we define interface wey dem call 'ISwapRouter'. Dis interface defines two fuktions 'exactInputSingle' and 'exactinput'.

## exactInputSingle

For line 25, we defines struct called 'ExactInputSingleParams'. Dis struct defines di parameters wey dey required for our exactInputSingle fuktion for line 21, which go execute one single hop swap. Dis struct get di following parameters:

- **`address tokenIn`**: Di address for di tokin being sent.
- **`address tokenOut`**: Di address for di tokin being received.
- **`uint24 fee`**: Di fee wey follow join di swap.
- **`address recipient`**: Di address wey go receive di output tokin.
- **`uint deadline`**: A timestamp by which di transaction must be processed, for time-limiting di swap.
- **`uint amountIn`**: Di amount of d input tokin being sent.
- **`uint amountOutMinimum`**: Di minimum amount of di output tokin wey we sender dey willing to accept, to protect against unfavorable price movements.
- **`uint160 sqrtPriceLimitX96`**: A limit for di price, represented for specifik format, to prevent di swap from occuring at unfavorable prices.

## exactInput

For line 25, we define a struct called 'ExactInputParams'. Dis struct defines di parameters wey dey required for our 'exactinput' fuktion for line 33. Dis funktion go execute a multi-hop swap. Dis struct get di following parameters:

- **`bytes path`**: Encoded info about di swap path (i.e., which tokins to swap through).
- **`address recipient`**: di address receiving di output tokins.
- **`uint deadline`**: Similar to above, a timestamp by which di transaction must dey processed.
- **`uint amountIn`**: Di amount of di input tokin.
- **`uint amountOutMinimum`**: Di minimum amount of di output tokin di sender dey expects receive.

