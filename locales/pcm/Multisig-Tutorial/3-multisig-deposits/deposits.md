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

For this section we go through the `receive` function and the deposit event wey join am. We go examine how di receive function dey use for deposit Ether inside di multi-signature wallet and how di Deposit event dey bring transparency.

## ⭐️ Assignment: Deposit Ether

Deposit 2 Ether inside di Multisig contract.

1. Deploy di Multisig contract like for di previous assignment.
2. Enta value of 2 Ether inside di Value field and select Ether for di dropdown menu.
3. For di bottom of your deployed contract inside di “Low level interactions” section click di “Transact” button.
4. For top of your deployed contract e go tal say “Balance: 2 Ether”.