In this section, we'll delve into the `swapExactInputMultiHop` function in the `UniswapV3SwapExamples` contract. This function enables more complex token swaps by allowing users to specify a custom path through multiple liquidity pools.

Si, par exemple, un utilisateur veut échanger le jeton A contre le jeton D, mais qu'il n'y a pas de pool de liquidités directe pour A et D, l'utilisateur peut spécifier un chemin à travers plusieurs jetons. Par exemple, l'utilisateur peut échanger A contre B, puis B contre C, et enfin C contre D. Ceci est bien sûr fait automatiquement par le contrat Uniswap V3 Swap.

### Paramètres et valeur de retour

On line 32, we define a function called `swapExactInputMultiHop`. This function executes a multi-hop swap. Il faut les paramètres suivants :

- **`bytes calldata path`** : Informations codées sur le chemin d'échange (c'est-à-dire les jetons à échanger).
- **`address tokenIn`**: The address of the token being sent.
- **`uint amountIn`**: The amount of the input token being sent.

It returns a `uint` called `amountOut`, which is the amount of the output token that was received.

### Function Body

Dans le corps de la fonction, nous transférons d'abord le jeton d'entrée de l'expéditeur à notre contrat, ligne 38.
Ensuite, nous approuvons le routeur Uniswap Swap pour dépenser le jeton d'entrée en notre nom, ligne 41.

Sur la ligne 43, nous créons une instance de la structure `ExactInputParams`, ligne 73. This struct contains the parameters that are required for our `exactInput` function on line 81, which will execute the multi-hop swap.

We set the parameters of the struct as follows:

- **`path`**: We set this to the `path` parameter of our function.
- **`destinataire`** : Nous avons défini cela sur l'expéditeur de la transaction.
- **`deadline`**: We set this to the current timestamp. We do this because we want the transaction to be processed as soon as possible.
- **`amountIn`**: We set this to the `amountIn` parameter of our function.
- **`amountOutMinimum`**: We set this to 0 because we do not want to specify a minimum amount of the output token that we are willing to accept.

On line 53, we execute the multi-hop swap by calling the `exactInput` function. This function returns the amount of the output token that was received.