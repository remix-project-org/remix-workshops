For dis we go explore di process of submitting and to confirm di transaction. Dis pocess dey neccessary wen de owner don change dier mind about de transaction and wetin go stop am from being executed. Dis section go dey straithfoward.

## dis na revokeConfirmation Event

On line we don add de RevokeConfirmation event. Dis event dey emmited whenever trasaction confirmation dey revoked by de owner.

## dis na revokeConfirmation Function

On line 129 we don add de RevokeConfirmation event. Im dey allow users to revoke transactioon confirmation.

De revokeConfirmation dey take one parameter: txlndex. Im get three modifiers: onlyOwner; txExist and no go dey Executed.

On line 134, we go require dat se transaction don dey confirmed by de caller. This one make sure say owner wey don confirm the transaction fit only revoke him own confirmation.
We don decrete de numConfirmations variable of de transaction and u go set de deyConfirmed we don dey map de transaction index and de address of de caller to false. Finally we go emit the `ConfirmTransaction` event.

## De conclusion

For dis we go explore di process of submitting and to confirm di transaction. We don examine de revokeConfirmation function and we don understand how im dey work to te allow users to revoke confirmations.

## De Assignment: u go Revoke Confirmation

U go confirm and u go revoke transaction to te send 2 Ether to de first accounts de "ACCOUNT" drop menu.

1. As for de previous assignment, u go deploy de Multisig contract u go send  de contract some Ether, and den u go submit transaction to dey first account for de "ACCOUNTS"  dropdown menu wey get value of 2 Ether.
2. U go confirm de transaction twice as de previous assignment wey dey.
3. U go revoke de transaction by to dey click revokeConfirmation and dey insert 0 as de transaction index. If u don click getTransaction again u suppose see dat de transaction don dey confirmed.

## De Final Conclusion

For dis tutorial we don exploi de process of creatind multi-signature wallet. We don learn how we go te initiate de contract, deposit Ether, submit, confirm and how we go te revoke transactions. We don learn how we go te execute transactions and how we go retrieve information about de multi-signature wallet.