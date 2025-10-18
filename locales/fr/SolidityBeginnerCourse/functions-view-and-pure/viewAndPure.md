This section will look into the types of functions that don't modify the state of the blockchain: _view_ and _pure_ functions.

### View Functions

_Afficher les fonctions_ promet de ne pas modifier l'état.

"Les déclarations suivantes sont considérées comme modifiant l'état :

1. Writing to state variables.
2. Émettre des événements.
3. Creating other contracts.
4. Using selfdestruct.
5. Sending Ether via calls.
6. Calling any function not marked view or pure.
7. Utilisation d'appels de bas niveau.
8. Using inline assembly that contains certain opcodes."

Extrait de la <0>documentation Solidity</0>.

You can declare a view function using the keyword `view`. Dans ce contrat, `addToX` (ligne 8) est une fonction d'affichage. This function takes the parameter `y` and returns the sum of the parameter and the state variable `x`. It reads `x` but does not modify it.

### Pure functions

_Pure functions_ promise to neither modify nor to read the state.

"En plus de la liste des déclarations de modification de l'état expliquée ci-dessus, les éléments suivants sont considérés comme lus à partir de l'État :

1. Reading from state variables.
2. Accéder à `address(this).balance` ou `<0>.balance`.
3. Accessing any of the members of block, tx, msg (with the exception of `msg.sig` and `msg.data`).
4. Calling any function not marked pure.
5. Using inline assembly that contains certain opcodes."

Extrait de la <0>documentation Solidity</0>.

You can declare a pure function using the keyword `pure`. In this contract, `add` (line 13) is a pure function. This function takes the parameters `i` and `j`, and returns the sum of them. It neither reads nor modifies the state variable `x`.

In Solidity development, you need to optimise your code for saving computation cost (gas cost). Declaring functions view and pure can save gas cost and make the code more readable and easier to maintain. Pure functions don't have any side effects and will always return the same result if you pass the same arguments.

<0>Regardez un tutoriel vidéo sur View et Pure Functions</0>.

## ⭐️ Assignment

Create a function called `addToX2` that takes the parameter `y` and updates the state variable `x` with the sum of the parameter and the state variable `x`.