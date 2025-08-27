For dis we go explore di process of submitting and to confirm di transaction.

## Di modifiers

We get new new modifiers for dis iteration. Make we examine nam one by one.

1. `txExists` modifier. (Line 13) dey make sure say the transaction dey real. E dey do this go tin by checking if the transaction index dey smaller than the length of the transaction array. We go look into dis modifier later on for dis section.
2. `notExecuted` modifier:\*\* (Line 18) dey ensures say the transaction never execute. E dey do dis by checking if the executed variable for the transaction dey false.
3. `notConfirmed` modifier:\*\* (Line 23) e dey make sure say the transaction never dey confirmed by the caller. E dey do dis thing by checking if `isConfirmed` mapping for the transaction index and the caller address dey false.

## Transaction Struct

For line 28, we get struct wey we deh call `Transaction`. We dey store struct members: `to`, `value`, `data`, `executed`, and `numConfirmations` for individual variables.

## Mapping of Confirmations

For line 37, we get mapping wey dem dey call `isConfirmed`. This mapping is used to keep track of the confirmations of each transaction. It maps the transaction's index to a mapping of an owner addresse to a boolean value. The boolean value indicates whether this owner has confirmed the transaction.

## Transactions Array

On line 39, we have an array called `transactions`. The array is used to store all the transactions submitted to the multi-signature wallet.

## Events

We have four new events in this iteration of the contract:

1. **`SubmitTransaction` event:** emitted whenever a transaction is submitted to the multi-signature wallet.
2. **`ConfirmTransaction` event:** emitted whenever a transaction is confirmed by an owner.
3. **`RevokeConfirmation` event:** emitted whenever a transaction confirmation is revoked by an owner.
4. **`ExecuteTransaction` event:** emitted whenever a transaction is executed.

## submitTransaction Function

The `submitTransaction` function (Line 78) allows users to submit a transaction to the multi-sig wallet. E go take three parameters: to`, `value`, and `data`. The `to`parameter is the address of the recipient of the transaction. The`value`parameter is the amount of Ether to be sent. The`data\` parameter is the data to be sent to the recipient. Only the owner fit submit transactions.

On line, 85 we create a new transaction struct and push it to the `transactions` array and emit the `SubmitTransaction` event. The `txIndex` variable is used to keep track of the transaction index.

## confirmTransaction Function

The `confirmTransaction` function (Line 98) allows users to confirm a transaction. It takes one parameter: `txIndex`.
It has three modifiers: `onlyOwner`, `txExists`, and `notExecuted`. The `onlyOwner` modifier ensures that only owners can confirm transactions. The `txExists` modifier ensures that the transaction exists. The `notExecuted` modifier ensures that the transaction has not been executed.

On line 101, we store the transaction in a local variable called `transaction`. We then increment the `numConfirmations` variable of the transaction and set the `isConfirmed` mapping of the transaction index and the caller's address to true. Finally, we emit the `ConfirmTransaction` event.

## executeTransaction Function

The `executeTransaction` function (Line 108) allows users to execute a transaction. On line 113, we require that the number of confirmations of the transaction is greater than or equal to the required number of confirmations. We then set the `executed` variable of the transaction to true. Finally, send the funds using the `call` function.  This is the `call` of the recipient address with the value and data of the transaction. If the transaction is successful, we emit the `ExecuteTransaction` event.

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
5. Switch to the second owner account and confirm the transaction again. If you click on `getTransaction` again, you should see that the transaction has been confirmed twice.
6. The last step is to execute the transaction. Click on `executeTransaction` and insert 0 as the transaction index. If you click on `getTransaction` again, you should see that the transaction has been executed. You can also check the balance of the first account in the "ACCOUNTS" dropdown menu. It should now be 2 Ether higher and the balance of the multi-signature wallet should be 2 Ether lower.

**Hint:**
If you submit a transaction make sure that the value is in Wei and that the _data field is correctly filled in. E.g. it could look like this: "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, 2000000000000000000, 0x" for 2 Ether.