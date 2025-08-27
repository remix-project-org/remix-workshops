For dis we go explore di process of submitting and to confirm di transaction. Dis pocess dey neccessary wen de owner don change dier mind about de transaction and wetin go stop am from being executed. Dis section go dey straithfoward.

## dis na revokeConfirmation Event

On line we don add de RevokeConfirmation event. Dis event dey emmited whenever trasaction confirmation dey revoked by de owner.

## dis na revokeConfirmation Function

On line 129, we have added the `revokeConfirmation` function. Im dey allow users to revoke transactioon confirmation.

De revokeConfirmation dey take one parameter: txlndex. Im get three modifiers: onlyOwner; txExist and no go dey Executed.

On line 134, we go require dat se transaction don dey confirmed by de caller. This ensures that an owner who has confirmed the transaction can only revoke their own confirmation.
We then decrement the `numConfirmations` variable of the transaction and set the `isConfirmed` mapping of the transaction index and the caller's address to false. Finally, we emit the `RevokeConfirmation` event.

## Conclusion

In this section, we explored the process of revoking confirmations. We examined the `revokeConfirmation` function and understood how it works to allow users to revoke confirmations.

## ⭐️ Assignment: Revoke a Confirmation

Confirm and revoke a transaction to send 2 Ether to the first account in the "ACCOUNTS" dropdown menu.

1. As in the previous assignment, deploy the Multisig contract, send the contract some Ether, and then  submit a transaction to the first account in the "ACCOUNTS" dropdown menu with a value of 2 Ether.
2. Confirm the transaction twice as in the previous assignment.
3. Revoke the transaction by clicking on `revokeConfirmation` and inserting 0 as the transaction index. If you click on `getTransaction` again, you should see that the transaction has been confirmed once.

## Final Conclusion

In this tutorial, we explored the process of creating a multi-signature wallet. We don learn how we go te initiate de contract, deposit Ether, submit, confirm and how we go te revoke transactions. We don learn how we go te execute transactions and how we go retrieve information about de multi-signature wallet.