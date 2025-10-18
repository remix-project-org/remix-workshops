For dis area we go explore di **initialization process** of the Multisig smart contract.We fit examine di constructor function and review how im set up di initial state of di contract.

## De note

For dis section dis tutorial fit build up ua mulstisig contract. In small section di contract fit become more complete.

## Di overview

Dis section di contract get events, state variables, modifiers and functions. **Events** provide transparency by logging specified activities on de blockchain, while **modifiers** ensure say na only authorized users can execute certain functions.

## Dis na State Variables

For line 4 we get de MultisigWallet contract itself. For di begining of di contract we get three state variables.

1. **`owners`:** An array containing de addresses of all im owners of de multi-signature wallet (Line 5).
2. **`isOwner`:** A mapping indicating whether an address na im owner (Line 6).
3. **`numConfirmationsRequired`:** de number of confirmations required for a transaction (Line 7).

Di setup of array and im mapping dey allow us collect di list of owners and verify whether an address na im owner.

## Di modifiers

Next we get modifiers wey dem call `onlyOwner` (Line 9). Modifiers in Solidity are special keywords that can be used to amend the behavior of functions. For our case di `onlyOwner` modifier ensures say na only owners can execute a function. E dey do am by checking whether di address of di **caller** is an owner.

## Di Constructor Function

Di costructor function (Line 14) is executed only once during de deployment of de contract. E dey initialize essential parameters, for dis case di list of owners and di required number of confirmations (line 14).

For line 15 and 16, we get two `require` statements to ensure that the inputs are valid. For dis case, e require say at least one owner and sat di number of required confirmations must be greater than zero and less than or di same as di number of owners.

Di constructor then go initializes di conntract state by verifying say address(0) (line25) and di owner is unique (Line 26).
E go add key/ value pair to di owner mapping (Line 28), and then e go populate di owner array with di provided owner addresses (Line 29).

E set di `numConfirmationsRequired` variable with the specified value (Line 32).

## na to getOwners Function

Di owners\`function(Line 36) allows users to fit retrieve di list of owners of the multi-signature wallet. E return di owners array (Line 37).

## na to getNumConfirmationsRequired Function

Di `getNumConfirmationsRequired` function (Line 41) allows yusers to retrieve the number of confirmations required for a transaction. E return di `numConfirmationsRequired` variable (Line 42).

## Di Conclusion

For dis area we go explore di initialization process of de Multisig smart contract. We dey examined di constructor function and understood how e set up di initial state of di contract.

## di Assignment: Deploy a Multisig Wallet

E deploy im mulstig contract with di three owners and e require two confirmations for transaction execution.

1. To fit compile contractInitialization.sol
2. U go deploy and run transactions in remix.
3. De Expand the "Deploy" section.
4. Na Under "_OWNERS", enter three an array of three addresses.
5. Under "_NUM_CONFIRMATIONS_REQUIRED", enter de number of confirmations required for im transaction.

di **Hints:**

- U fit get address from di "ACCOUNTS" dropdown menu.
- Di array of adddresses must be for di format: ["0x123...", "0x456...", "0x789..."].