L'exécutable Axelar contient des fonctions d'aide pertinentes qui seront automatiquement exécutées sur la chaîne de destination en correspondance avec la transaction entrante pertinente de la chaîne source.

Voici les fonctions pertinentes que vous devrez utiliser à partir d'Axelar Executable

## \_execute()

Cette fonction gère l'exécution sur la chaîne de destination. It takes the following four parameters:

1. `commandId`: A unique transaction id on the Axelar chain.
2. `sourceChain` : La blockchain à partir de laquelle la transaction a été envoyée
3. `sourceAddress`: The address from the source chain that the transaction has been sent from
4. `payload` : Le message qui est envoyé

Les `sourceChain` et `sourceAddress` sont des paramètres clés que vous recevez prêts à l'emploi et qui peuvent être utilisés pour vérifier l'authenticité des messages sur la chaîne de destination. The payload (as discussed in the gateway section) is the message that was sent from the source chain to be used on your destination chain. The `commandId` will not be used during the rest of this module.

## \_executeWithToken()

Cette fonction gère l'exécution sur la chaîne de destination pour un message envoyé avec un jeton fongible. Il faut six paramètres pertinents :

1. `commandId`: A unique transaction id on the Axelar chain.
2. `sourceChain`: The blockchain which the transaction has been sent from
3. `sourceAddress`: The address from the source chain that the transaction has been sent from
4. `payload`: The message that is being sent
5. `tokenSymbol`: The symbol of the token being sent
6. `montant` : Le montant de ce jeton qui est envoyé

The first four parameters are identical to that of the `_execute()` function. The final two parameters of `tokenSymbol` and `amount` are in reference to the token that is being sent along with the message. It allows you on the destination chain to interact with the token accordingly, for example transferring it to another receiving address. The `commandId` will not be used during the rest of this module.
