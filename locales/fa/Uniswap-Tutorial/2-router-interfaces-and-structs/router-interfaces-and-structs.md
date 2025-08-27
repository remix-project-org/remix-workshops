کل قرارداد UniswapSwapExamples تنها در بخش ۵ این آموزش ارائه خواهد شد.  قبل از آن، ما بلوک‌های کد را ایجاد خواهیم کرد.

این بخش به بررسی رابط `ISwapRouter` می‌پردازد که توابعی را تعریف می‌کند که می‌توان روی قرارداد مبادله Uniswap فراخوانی کرد.

تبادلات تک‌گام به کاربران اجازه می‌دهد تا یک توکن را مستقیماً در یک استخر نقدینگی با توکن دیگر مبادله کنند.
تبادلات چند مرحله‌ای به کاربران اجازه می‌دهد تا یک توکن را برای توکن دیگر از طریق چندین توکن مبادله کنند.

رابط‌ها در سالیدیتی توابعی را مشخص می‌کنند که باید در قراردادی که آن‌ها را به ارث می‌برد، گنجانده شوند.  آنها برای اعلام اینکه چه عملکردهایی پشتیبانی می‌شوند و همچنین برای تسهیل ادغام و تعامل بین قراردادهای مختلف مفید هستند.

Structs are used to define custom data types.

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

