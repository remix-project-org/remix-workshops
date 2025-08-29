Le service de gaz Axelar est un outil extrêmement utile mis à disposition pour payer le gaz pour une transaction inter-chaînes. It allows you to pay for the cost of a transaction in the token of the source chain, making for a much easier end user (and developer) experience. If for example the source chain is Ethereum and the destination chain is Polygon then the gas service will receive the complete payment for the transaction in ETH and no matic is needed from the caller to pay for the execution on the Polygon destination chain.

The following are the two more relevant functions you will need to be familiar with in regards to the Gas Service.

## payNativeGasForContractCall()

This function allows you to pay for the entirety of an interchain transaction in the native token of the source chain. Il faut cinq paramètres pertinents :

1. `expéditeur` : L'adresse effectuant le paiement
2. `destinationAddress`: The address on the destination chain the transaction is sent to
3. `destinationChain`: The name of the destination the transaction is sent to
4. `payload`: The message that is being sent
5. `refundAddress` : L'adresse à laquelle tout remboursement doit être envoyé si trop de gaz a été envoyé avec cette transaction.

The parameters overlap with the parameters required by the `callContract()` function in the Gateway contract. The two parameters not discussed in the Gateway section are `sender` and `refundAddress`. The sender is the address paying for the transaction and the refund address is the address that will receive any surplus funds sent to the gas service.

## payNativeGasForContractCallWithToken()

This function allows you to pay for the entirety of an interchain transaction (that includes a token transfer) in the native token of the source chain. It takes seven relevant parameters:

1. `sender`: The address making the payment
2. `destinationAddress`: The address on the destination chain the transaction is sent to
3. `destinationChain`: The name of the destination the transaction is sent to
4. `payload`: The message that is being sent
5. `symbol`: The symbol of the token that was sent
6. `amount`: The amount of the token that was sent
7. `refundAddress` : L'adresse à laquelle tout remboursement doit être envoyé si trop de gaz a été envoyé avec cette transaction.

Cette fonction est presque identique à la première, la principale différence étant qu'elle est utilisée pour les transactions de transfert de messages + jetons par opposition aux simples transactions de messages interchaînes (alias GMP Transactions). As a result the GasService needs to also know the `symbol` and `amount` of the token that is being sent.
