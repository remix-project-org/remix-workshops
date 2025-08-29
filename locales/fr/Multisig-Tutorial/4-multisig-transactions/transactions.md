Dans cette section, nous allons explorer le processus de soumission et de confirmation des transactions.

## Modifiers

Nous avons de nouveaux modificateurs dans cette itération du contrat. Let's examine them one by one.

1. **`txExists` modifier:** (Line 13) ensures that the transaction exists. It does this by checking whether the transaction index is less than the length of the `transactions` array. We'll go into more about in this modifier later in this section.
2. **`notExecuted` modifier:** (Line 18) ensures that the transaction has not been executed. It does this by checking whether the `executed` variable of the transaction is false.
3. **`notConfirmed` modifier:** (Line 23) ensures that the transaction has not been confirmed by the caller. It does this by checking whether the `isConfirmed` mapping of the transaction index and the caller's address is false.

## Transaction Struct

Sur la ligne 28, nous avons une structure appelée `Transaction`. We store the struct members: `to`, `value`, `data`, `executed`, and `numConfirmations` in individual variables.

## Mapping of Confirmations

On line 37, we have a mapping called `isConfirmed`. This mapping is used to keep track of the confirmations of each transaction. Il mappe l'index de la transaction à un mappage d'une adresse du propriétaire à une valeur booléenne. La valeur booléenne indique si ce propriétaire a confirmé la transaction.

## Tableau des transactions

On line 39, we have an array called `transactions`. The array is used to store all the transactions submitted to the multi-signature wallet.

## Events

We have four new events in this iteration of the contract:

1. **`SubmitTransaction` événement :** émis chaque fois qu'une transaction est soumise au portefeuille multi-signature.
2. **`ConfirmTransaction` event:** emitted whenever a transaction is confirmed by an owner.
3. **`RevokeConfirmation` event:** emitted whenever a transaction confirmation is revoked by an owner.
4. **`ExecuteTransaction` event:** emitted whenever a transaction is executed.

## submitTransaction Function

La fonction `submitTransaction` (ligne 78) permet aux utilisateurs de soumettre une transaction au portefeuille multi-sig. It takes three parameters: `to`, `value`, and `data`. Le paramètre `to` est l'adresse du destinataire de la transaction. The `value` parameter is the amount of Ether to be sent. The `data` parameter is the data to be sent to the recipient. Only owners can submit transactions.

En ligne, 85, nous créons une nouvelle structure de transaction et la poussons vers le tableau `transactions` et émettons l'événement `SubmitTransaction`. La variable `txIndex` est utilisée pour suivre l'index des transactions.

## confirmTransaction Function

La fonction `confirmTransaction` (ligne 98) permet aux utilisateurs de confirmer une transaction. It takes one parameter: `txIndex`.
Il a trois modificateurs : `onlyOwner`, `txExists` et `notExecuted`. The `onlyOwner` modifier ensures that only owners can confirm transactions. The `txExists` modifier ensures that the transaction exists. The `notExecuted` modifier ensures that the transaction has not been executed.

On line 101, we store the transaction in a local variable called `transaction`. We then increment the `numConfirmations` variable of the transaction and set the `isConfirmed` mapping of the transaction index and the caller's address to true. Finally, we emit the `ConfirmTransaction` event.

## executeTransaction Function

La fonction `executeTransaction` (ligne 108) permet aux utilisateurs d'exécuter une transaction. On line 113, we require that the number of confirmations of the transaction is greater than or equal to the required number of confirmations. We then set the `executed` variable of the transaction to true. Finally, send the funds using the `call` function.  This is the `call` of the recipient address with the value and data of the transaction. If the transaction is successful, we emit the `ExecuteTransaction` event.

## getTransactionCount Function

The `getTransactionCount` function (Line 132) allows users to retrieve the number of transactions in the multi-signature wallet. It returns the length of the `transactions` array.

## getTransaction Function

The `getTransaction` function (Line 136) allows users to retrieve a transaction. It returns the transaction struct members that we explored earlier in this section.

## Conclusion

In this section, we explored the process of submitting, confirming, and executing transactions. We examined the `submitTransaction`, `confirmTransaction`, and `executeTransaction` functions and understood how they work together to allow multiple users to submit and confirm transactions.

## ⭐️ Assignment: Make a Transaction

Submit, confirm, and execute a transaction to send 2 Ether to the first account in the "ACCOUNTS" dropdown menu.

1. Deploy the Multisig contract as in the previous assignment. Make sure that the required number of confirmations is 2.
2. Fund the multisig from any address by sending 4 Ether as you did in the previous assignment.
3. Try sending 2 Ether to the first account in the "ACCOUNTS" dropdown menu.  Once you have submitted this transaction (with submitTransaction), click on `getTransactionCount` and should see one transaction or you can click on `getTransaction`, insert 0 as the transaction index and see the transaction you just submitted.
4. Now you can click on `confirmTransaction` and insert 0 as the transaction index. If you click on `getTransaction` again, you should see that the transaction has been confirmed once.
5. Passez au deuxième compte propriétaire et confirmez à nouveau la transaction. If you click on `getTransaction` again, you should see that the transaction has been confirmed twice.
6. The last step is to execute the transaction. Cliquez sur `executeTransaction` et insérez 0 comme index de transaction. If you click on `getTransaction` again, you should see that the transaction has been executed. You can also check the balance of the first account in the "ACCOUNTS" dropdown menu. It should now be 2 Ether higher and the balance of the multi-signature wallet should be 2 Ether lower.

**Hint:**
If you submit a transaction make sure that the value is in Wei and that the _data field is correctly filled in. E.g. it could look like this: "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, 2000000000000000000, 0x" for 2 Ether.