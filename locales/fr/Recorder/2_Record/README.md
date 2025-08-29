# Setting up a tedious series of steps

## Following this could get tedious but that's the point.

We are going to:

- Deploy a voting contract where there are 3 proposals input in the constructor.
- Donnez des privilèges de vote à 2 adresses supplémentaires (nous avons donc un total de 3 adresses de vote).
- Faites voter une adresse pour la proposition 1 (index basé sur l'indice de 0) et les deux autres pour la proposition 2.

1. Take the 3_Ballot.sol from the sample solidity files and compile it.  Then go to the **Deploy & Run** Module.

2. Sélectionnez l'environnement **JavaScript VM**.

3. Dans le paramètre du constructeur - mettez dans **["0x5031000000000000000000000000000000000000000000000000000000000000", "0x503200000000000000000000000000000000000000000000000000000000000", "0x503300000000000000000000000000000000000000000000000000000000000"]** Cliquez sur le bouton **Déployer** Cliquez sur le bouton **Déployer**.

4. Open up the deployed contract.

5. In the **vote** function put in 2.  This means that you as the msg.sender & chairperson are voting for proposal at position 2, which is the last proposal in our list.

6. Now you need to give other addresses the right to vote.  Select another address in the **account** pulldown and copy it and then **go back to the 1st address**.  Collez l'adresse de copie dans la zone de texte à côté de la fonction giveRightToVote.  And again, select another address and copy it and **then go back to the 1st address** again and paste it into giveRightToVote.

7. Now you have 3 addresses with the right to vote.

8. Passez à l'une des adresses auxquelles vous avez donné le droit de vote et votez pour la proposition **1**.  (Mettez **1** dans la zone de texte à côté de la fonction de vote).  And then switch to the other address and vote for proposal **2** with that one.

9. Open up the **Transactions recorded** section of the module - by clicking on the caret. Cliquez sur l'icône du disque dur dans la section **Transactions enregistrées** pour enregistrer vos étapes.
   ![recorder](https://github.com/ethereum/remix-workshops/blob/master/Recorder/2_Record/images/recorder.png?raw=true "recorder")

10. You will get a modal window that tells you it wants to save a file called **scenario.json**.  Click OK.

11. Click on the function **winningProposal** to confirm that the final proposal won - which is the proposal at position 2 in the array. **0: uint256: winningProposal_ 2**
