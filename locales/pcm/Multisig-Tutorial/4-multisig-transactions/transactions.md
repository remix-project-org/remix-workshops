For dis we go explore di process of submitting and to confirm di transaction.

## Di modifiers

We get new new modifiers for dis iteration. Make we examine nam one by one.

1. `txExists` modifier. (Line 13) dey make sure say the transaction dey real. E dey do this go tin by checking if the transaction index dey smaller than the length of the transaction array. We go look into dis modifier later on for dis section.
2. `notExecuted` modifier:\*\* (Line 18) dey ensures say the transaction never execute. E dey do dis by checking if the executed variable for the transaction dey false.
3. `notConfirmed` modifier:\*\* (Line 23) e dey make sure say the transaction never dey confirmed by the caller. E dey do dis thing by checking if `isConfirmed` mapping for the transaction index and the caller address dey false.

## Transaction Struct

For line 28, we get struct wey we deh call `Transaction`. We dey store struct members: `to`, `value`, `data`, `executed`, and `numConfirmations` for individual variables.

## Mapping of Confirmations

For line 37, we get mapping wey dem dey call `isConfirmed`. The mapping dey used to observe confirmation for every transaction. E map the transaction index go one mapping of owner address to boolean value. Na the boolean number dey show if the owner don confirm the transaction.

## Transactions Array

For line 39, we get one array wey we dey call `transactions`. The array dey used to store every transaction wey dey submitted go multi signature wallet.

## Events

We get four new events inside this iteration of the contract:

1. `SubmitTransaction` event:\*\* e dey emit anytime transaction dey submitted for the multi-signature wallet.
2. `ConfirmTransaction` event: e dey emit anytime transaction dey confirmed by any owner.
3. `RevokeConfirmation` event: e dey emit anytime wey the owner dey revoke the transaction conformation.
4. `ExecuteTransaction` event: e dey emit anytime wey transaction don finish dey run.

## submitTransaction Function

The `submitTransaction` function (Line 78) dey allows users submit transaction go the multi-sig wallet. E go take three parameters: to`, `value`, and `data`. The `to\` parameter na address of the person wey reveive the transaction. The value parameter na the amount of ether wey we suppose send. The data parameter na the data wey dem send go the person wey dey collect am. Only the owner fit submit transactions.

For line 85, we create new transaction struct, push am go the transactions array, then emit the SubmitTransaction event. The `txIndex` variable na wetin we go use keep track of the transaction index.

## confirmTransaction Function

The `confirmTransaction` function (Line 98) dey allow people confirm transaction. E go take one parameter: `txIndex`.
E get three modifiers `onlyOwner`, `txExists`, and `notExecuted`. The `onlyOwner` modifier dey make sure say na only owners fit confirm transactions. The `txExists` modifier dey make sure say the transaction dey. The `notExecuted` modifier dey make sure say the transaction never execute.

For line 101, we save the transaction for local variable called `transaction`. We go con increase the `numConfirmations` variable for the transaction con set the `isConfirmed` mapping for the transaction index and the caller address go true. Finally we go emit the `ConfirmTransaction` event.

## executeTransaction Function

The `executeTransaction` function (Line 108) dey make users do transaction. For line 113 we require say the number of confirmations wey dey the transaction dey bigger than or equal to the number wey the confirmations require. We go come set the executed variable wey dey the transaction to true. Finally, send the funds using the `call` function.  Na the call of the recipient address with the value and data wey dey the transaction. If the transaction dey successful we go emit the `ExecuteTransaction` event.

## getTransactionCount Function

The `getTransactionCount` function (Line 132) go allow users to retrieve the number of transactions wey dey the multi-signature wallet. E dey give back the length for the transaction array.

## getTransaction Function

The `getTransaction` function (Line 136) dey allow people retrieve one transaction. E dey give back the transaction struct member wey we see together for this section.

## Conclusion

For this section we explore the process on how u go submit, confirm and execute transactions. We examined the `submitTransaction`, `confirmTransaction`, and `executeTransaction` functions and understood how they work together to allow multiple users to submit and confirm transactions.

## ⭐️ Assignment: Make a Transaction

Submit, confirm, and execute a transaction to send 2 Ether to the first account in the "ACCOUNTS" dropdown menu.

1. Deploy the Multisig contract as in the previous assignment. Make sure say the required number of the confirmations na 2.
2. Fund the multisig from any address by sending 4 Ether as u do am for the previous assignment.
3. Try send 2 Ether go the first account in "ACCOUNTS" dropdown menu.  Once u don sumbit this transaction (with submitTransaction), click that `getTransactionCount` u go come see one transaction or u fit click on `getTransaction`,
   put 0 as the transaction index then see the transaction wey u just submit.
4. Now u fit click on `confirmTransaction` and insert 0 as the transaction index. If you click that `getTransaction` again u go see say the transaction go confirm once.
5. Switch go the second owner account then confirm the transaction again. If you click that `getTransaction` again, you go see say the transaction don confirm twice.
6. The last step na to execute the transaction. Click on `executeTransaction` then insert 0 as the transaction index. If you click that `getTransaction` again, you go see say the transaction don dey executed. U fit also check the balance of the first account for "ACCOUNTS" dropdown menu. E go come be 2 Ether higher and the balance of the multi-signature wallet go come be 2 Ether lower.

**Hint**
If u submit one transaction make sure say the valid dey inside Wei and the _data field dey correct. E.g. e fit look like this: "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4, 2000000000000000000, 0x" for 2 Ether.