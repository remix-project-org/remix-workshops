Single-hop swaps allow users to exchange one token for another directly within a liquidity pool. In this section, we will learn how to use the Uniswap V3 Swap contract to execute single-hop swaps.

## Function Parameters

On line 8, we define a function called `swapExactInputSingleHop`. This function executes a single-hop swap. It takes the following parameters:

- **`address tokenIn`** : L'adresse du jeton envoyé.
- **`address tokenOut`** : L'adresse du jeton reçu.
- **`uint24 poolFee`** : Les frais associés à l'échange.
- **`uint amountIn`**: The amount of the input token being sent.

It returns a `uint` called `amountOut`, which is the amount of the output token that was received.

## Function Body

In the function body, we first transfer the input token from the sender to our contract, line 14.
Ensuite, nous approuvons le contrat Uniswap Swap pour dépenser le jeton d'entrée en notre nom, ligne 15.

On line 17, we create an instance of the `ExactInputSingleParams` struct. This struct contains the parameters that are required for our `exactInputSingle` function on line 45, which will execute the single-hop swap. We repeat `ISwapRouter.ExactInputSingleParams` two times on that line because we are making an instance of a struct that is defined in an interface.

## Parameters of the ExactInputSingleParams Struct

We set the parameters of the struct as follows:

- **`tokenIn`** : Nous définissons cela sur le paramètre `tokenIn` de notre fonction.
- **`tokenOut`** : Nous définissons cela sur le paramètre `tokenOut` de notre fonction.
- **`fee`**: We set this to the `poolFee` parameter of our function.
- **`destinataire`** : Nous avons défini cela sur l'expéditeur de la transaction.
- **`date limite`** : Nous l'avons fixé à l'horodatage actuel. Nous faisons cela parce que nous voulons que la transaction soit traitée dès que possible.
- **`amountIn`** : Nous définissons ceci sur le paramètre `amountIn` de notre fonction.
- **`amountOutMinimum`** : Nous définissons cela à 0 parce que nous ne voulons pas spécifier une quantité minimale du jeton de sortie que nous sommes prêts à accepter.
- **`sqrtPriceLimitX96`** : Nous l'avons fixé à 0 parce que nous ne voulons pas spécifier de limite sur le prix.

## Executing the Single-hop Swap

À la ligne 29, nous assignons la sortie de la fonction `exactInputSingle` à la variable `amountOut`. This function executes the single-hop swap and returns the amount of the output token that was received.