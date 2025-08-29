In this section, we'll explore the **initialization process** of the Multisig smart contract. We'll examine the constructor function and review how it sets up the initial state of the contract.

## Note

From this section on in this tutorial, we will be building up a multisig contract. In subsequent sections, the contract will become increasingly complete.

## Overview

Dans cette section, le contrat se compose d'événements, de variables d'état, de modificateurs et de fonctions. **Events** provide transparency by logging specified activities on the blockchain, while **modifiers** ensure that only authorized users can execute certain functions.

## State Variables

In Line 4, we have the MultisigWallet contract itself. At the beginning of the contract, we have three state variables.

1. **`owners`:** An array containing the addresses of all owners of the multi-signature wallet (Line 5).
2. **`isOwner`:** A mapping indicating whether an address is an owner (Line 6).
3. **`numConfirmationsRequired`:** The number of confirmations required for a transaction (Line 7).

The setup of array and mapping allows us to easily retrieve the list of owners and verify whether an address is an owner.

## Modifiers

Next, we have a modifier called `onlyOwner` (Line 9). Modifiers in Solidity are special keywords that can be used to amend the behavior of functions. In our case, the `onlyOwner` modifier ensures that only owners can execute a function. It does this by checking whether the address of the **caller** is an owner.

## Constructor Function

The `constructor` function (Line 14) is executed only once during the deployment of the contract. Il initialise les paramètres essentiels, dans ce cas, la liste des propriétaires et le nombre requis de confirmations (ligne 14).

On lines 15 and 16, we have two `require` statements to ensure that the inputs are valid. Dans ce cas, nous exigeons qu'il y ait au moins un propriétaire et que le nombre de confirmations requises soit supérieur à zéro et inférieur ou égal au nombre de propriétaires.

The constructor then initializes the contract state by verifying that is not address(0) (Line 25) and that the owner is unique (Line 26).  Then it adds a key/ value pair to the isOwner mapping (Line 28), and then it populates the `owners` array with the provided owner addresses (Line 29).

Enfin, il définit la variable `numConfirmionsRequired` avec la valeur spécifiée (ligne 32).

## getOwners Function

The `getOwners` function (Line 36) allows users to retrieve the list of owners of the multi-signature wallet. Il renvoie le tableau `owners` (ligne 37).

## getNumConfirmationsRequired Function

La fonction `getNumConfirmationsRequired` (ligne 41) permet aux utilisateurs de récupérer le nombre de confirmations requises pour une transaction. It returns the `numConfirmationsRequired` variable (Line 42).

## Conclusion

In this section, we explored the initialization process of the Multisig smart contract. We examined the constructor function and understood how it sets up the initial state of the contract.

## ⭐️ Assignment: Deploy a Multisig Wallet

Deploy a Multisig contract with three owners and require two confirmations for transaction execution.

1. Compile contractInitialization.sol
2. Go to Deploy & Run Transactions in Remix.
3. Expand the "Deploy" section.
4. Under "_OWNERS", enter three an array of three addresses.
5. Under "_NUM_CONFIRMATIONS_REQUIRED", enter the number of confirmations required for a transaction.

**Indices:**

- You can get addresses from the "ACCOUNTS" dropdown menu.
- The array of addresses should be in the format: ["0x123...", "0x456...", "0x789..."].