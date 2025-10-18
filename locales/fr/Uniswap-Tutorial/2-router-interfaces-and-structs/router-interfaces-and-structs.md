The entire UniswapSwapExamples contract will only be presented in section 5 of this tutorial.  Before then, we'll build up blocks of code.

Cette section explore l'interface `ISwapRouter`, qui définit les fonctions qui peuvent être appelées sur le contrat Uniswap Swap.

Single-hop swaps allow users to exchange one token for another directly within a liquidity pool.
Multi-hop swaps allow users to exchange one token for another by routing through multiple tokens.

Les interfaces dans Solidity spécifient les fonctions qui doivent être incluses dans un contrat qui en hérite.  They are useful for declaring what functions be supported and allow for easier integration and interaction between different contracts.

Structs are used to define custom data types.

## ISwapRouter Interface

L'interface ISwapRouter définit les fonctions qui peuvent être appelées sur le contrat Uniswap Swap. We will need to use this interface to interact with the Uniswap Swap contract and execute swaps.

On line 5, we define a constant variable called `router` that is of type `ISwapRouter`. We set the value of this variable to the interface instance of a smart contract that is deployed at the address `0xE592427A0AEce92De3Edee1F18E0157C05861564`. This is the address of the Uniswap V3 Swap contract on the Ethereum mainnet.

On line 9, we define an interface called `ISwapRouter`. This interface defines two functions: `exactInputSingle` and `exactInput`.

## exactInputSingle

On line 25, we define a struct called `ExactInputSingleParams`. This struct defines the parameters that are required for our exactInputSingle function on line 21, which will execute a single-hop swap. The struct has the following parameters:

- **`address tokenIn`**: The address of the token being sent.
- **`address tokenOut`**: The address of the token being received.
- **`uint24 fee`**: The fee associated with the swap.
- **`adresse destinataire`** : L'adresse qui recevra le jeton de sortie.
- **`uint deadline`**: A timestamp by which the transaction must be processed, for time-limiting the swap.
- **`uint amountIn`** : Le montant du jeton d'entrée envoyé.
- **`uint amountOutMinimum`**: The minimum amount of the output token that the sender is willing to accept, to protect against unfavorable price movements.
- **`uint160 sqrtPriceLimitX96`**: A limit on the price, represented in a specific format, to prevent the swap from occurring at unfavorable prices.

## exactInput

On line 25, we define a struct called `ExactInputParams`. Cette structure définit les paramètres requis pour notre fonction `exactInput` à la ligne 33. This function will execute a multi-hop swap. The struct has the following parameters:

- **`bytes path`**: Encoded information about the swap path (i.e., which tokens to swap through).
- **`adresse destinataire`** : L'adresse recevant les jetons de sortie.
- **`uint deadline`**: Similar to above, a timestamp by which the transaction must be processed.
- **`uint amountIn`** : Le montant du jeton d'entrée.
- **`uint amountOutMinimum`**: The minimum amount of the output token the sender expects to receive.

