À ce stade, nous avons passé en revue un exemple de la façon d'envoyer un message général entre une blockchain et une autre. Maintenant, mettons en œuvre un contrat qui envoie un message et un jeton d'une blockchain à une autre.

## Overview

This contract should seem largely familiar. Much like the previous section the `constructor` receives the `Gateway` and `Gas Service` addresses.

It then has a function that will be called from the source chain called `sendToMany` that takes in parameters similar to the previous section.

1. `_destinationChain`: The chain the transaction is sending to
2. `_destinationAddress` : L'adresse de la chaîne de destination à laquelle votre transaction est envoyée
3. `_destinationAddresses` : Le message que vous enverrez avec votre transfert de jeton. Dans cet exemple, le message est une liste d'adresses de réception pour le transfert de jeton.
4. `_symbol`: The symbol of the token address being sent
5. `_amount` : Le montant du jeton envoyé

In the function we already have the `require` statement implemented to ensure gas is sent

We also have the basic ERC20 functionality to send the token from the calling wallet to this smart contract. Le contrat appelle également la fonction "approuver" pour permettre à la passerelle de transférer éventuellement des fonds en son nom.

Enfin, la fonction `_executeWithToken()` est également implémentée prête à l'emploi.

It makes use of the following params:

1. `_payload`: The incoming message from the source chain
2. `_tokenSymbol` : Le symbole du jeton qui a été envoyé à partir de la chaîne source
3. `_amount`: The amount of the token that was sent from the source chain

Now with these params that were passed in, the `_execute()` function can send the tokens that were sent to the appropriate receivers.

## Défi

Your challenge here is to finish off the `sendToMany()` function using the Axelar Gateway and Gas Service to trigger an interchain transaction.

En fin de compte, vous devriez être en mesure de déployer ce contrat sur deux réseaux de test, de déclencher la fonction `sendToMany()` et de voir la transaction en direct sur <0>Axelarscan (testnet) block explorer</0>.

### Notes de test

Note 1 : L'ERC20 recommandé à utiliser est `aUSDC`, une version enveloppée du jeton USDC qui peut être obtenue à partir de <0>le bot robinet discord</0>. Lors du déclenchement de la fonction `sendToMany()`, il suffit de passer le symbole `aUSDC` au quatrième param.

Remarque 2 : Lors du déclenchement de la fonction `sendToMany()`, vous devez vous rappeler d'approuver`votre contrat pour dépenser des jetons`aUSDC`en votre nom, sinon`transferFrom()\` sur la ligne49 lancera une erreur.
