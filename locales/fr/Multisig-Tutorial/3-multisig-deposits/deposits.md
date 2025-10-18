In this section, we'll explore the `receive` function and the associated Deposit event. We'll examine how the `receive` function is used to deposit Ether into the multi-signature wallet and how the Deposit event provides transparency.

## Deposit Event

On line, 9 we have the Deposit event. L'événement de dépôt est émis chaque fois que l'éther est déposé dans le portefeuille multi-signature. It includes three parameters:

1. `sender`: The address that sent the Ether.
2. `amount`: The amount of Ether deposited.
3. `balance`: The updated balance of the contract after the deposit.

Nous pouvons utiliser l'événement de dépôt pour suivre le flux d'éther dans le portefeuille multi-signature et peut-être déclencher d'autres actions en fonction de l'événement.

## receive Function

On line 43, we have the `receive` function. La fonction `receive` est une fonction spéciale qui est exécutée chaque fois que Ether est envoyé au contrat.

The `receive` function is marked as `external` and `payable`. The `external` modifier means that the function can only be called from outside the contract. The `payable` modifier means that the function can receive Ether.

The `receive` function emits the Deposit event (Line 44) with the address of the sender, the amount of Ether sent, and the updated balance of the contract. Il ne retourne rien.

To receive Ether, a contract must have a `receive`, `fallback`, or a function with the `payable` modifier. Si aucun d'entre eux n'est présent, le contrat rejettera tout Ether qui lui est envoyé.

## Conclusion

In this section, we explored the `receive` function and the associated Deposit event. We examined how the `receive` function is used to deposit Ether into the multi-signature wallet and how the Deposit event provides transparency.

## ⭐️ Affectation : Dépôt d'éther

Déposez 2 Ether dans le contrat Multisig.

1. Déployer le contrat Multisig comme dans l'affectation précédente.
2. Entrez une valeur de 2 Ether dans le champ Valeur et sélectionnez Ether dans le menu déroulant.
3. At the bottom of your deployed contract in the "Low level interactions" section, click on the "Transact" button.
4. En plus de votre contrat déployé, il devrait maintenant dire "Solde : 2 Ether".