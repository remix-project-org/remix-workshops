For dis section, we go explore di receive function and di associated Deposit event. We go examine how di receive function dey use for deposit Ether inside di multi-signature wallet and how di Deposit event dey bring transparency.

## Deposit Event

On line, 9 we get di Deposit event. Di Deposit event dey emit weneva Ether dey enta inside di multi-signature wallet. E get three parameta:

1. `sender`: De address wey send di Ether.
2. `amount`: De amount of Ether wey dem deposit.
3. balance: Di updated balance of di contract after di deposit.

We fit use di Deposit event track di flow of Ether inside di multi-signature wallet and maybe trigger other actions based on di event.

## receive Function

For line 43, we get the `receive` function. Di receive function na special function wey dey executed whenever Ether dey sent go di contract.

Di receive function dey marked as external and payable. Di external modifier mean say di function fit only dey called from outside di contract. Di payable modifier mean say di function fit collect Ether.

Di receive function dey emit di Deposit event (Line 44) with di address of di sender di amount of Ether wey dey sent and di updated balance of di contract. E no dey send back anytin.

For enta Ether, contract must to get receive fallback or function wey get di payable modifier. If none of these are present, the contract will reject any Ether sent to it.

## Conclusion

In this section, we explored the `receive` function and the associated Deposit event. We examined how the `receive` function is used to deposit Ether into the multi-signature wallet and how the Deposit event provides transparency.

## ⭐️ Assignment: Deposit Ether

Deposit 2 Ether into the Multisig contract.

1. Deploy the Multisig contract as in the previous assignment.
2. Enter a Value of 2 Ether in the Value field and select Ether in the dropdown menu.
3. At the bottom of your deployed contract in the "Low level interactions" section, click on the "Transact" button.
4. On top of your deployed contract, it should now say "Balance: 2 Ether".