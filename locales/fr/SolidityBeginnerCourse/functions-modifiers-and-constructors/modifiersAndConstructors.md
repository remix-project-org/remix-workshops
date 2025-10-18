Dans cette section, nous allons apprendre à modifier le comportement d'une fonction et à exécuter le code d'initialisation du contrat.

### Function Modifier

_Function Modifiers_ are used to change the behavior of a function. Par exemple, ils vérifient souvent une condition avant d'exécuter une fonction pour restreindre l'accès ou valider les entrées.

This first part of this contract is about changing ownership of a contract. La propriété dans ce contrat est exprimée par la valeur de la variable d'état `owner` qui est du type `address` (ligne 7).

The function `changeOwner` (line 33) can change this ownership. It takes an input parameter of the type `address` and assigns its value to the state variable `owner`.

Cependant, cette fonction ne peut pas simplement être exécutée sous toutes les conditions ; elle a deux modificateurs, `onlyOwner` et `validAddress`.

Let's look at `onlyOwner` first (line 18).
Les modificateurs de fonction sont définis avec le mot-clé `modifier` et un nom unique ; ils peuvent également avoir des paramètres.

The underscore `_` (line 23) is used inside modifiers to represent the rest of the code that will be executed in the body of the modified function.
The code you place before the underscore in the modifier will be executed before the code in the body of the modified function. The code after the underscore will be executed after the code in the body of the modified function.

Dans ce cas, la fonction `require` (ligne 19) vérifie si l'adresse exécutant le contrat est la même que la valeur stockée dans la variable `owner`. If it is, the rest of the code will be executed, otherwise it will throw an error.

Vous pouvez en apprendre plus sur `assert` et `require` dans la <0>Documentation Solidity</0>, ils sont utilisés pour vérifier les conditions et lancer des erreurs si elles ne sont pas remplies.

The `validAddress` modifier (line 28) has a parameter of type `address` and checks if the provided address is valid. If it is, it continues to execute the code.

### Constructor

A constructor function is executed upon the creation of a contract. Vous pouvez l'utiliser pour exécuter le code d'initialisation du contrat. The constructor can have parameters and is especially useful when you don't know certain initialization values before the deployment of the contract.

You declare a constructor using the `constructor` keyword. The constructor in this contract (line 11) sets the initial value of the owner variable upon the creation of the contract.

<0>Regardez un tutoriel vidéo sur les modificateurs de fonction</0>.

## ⭐️ Assignment

1. Create a new function, `increaseX` in the contract. La fonction doit prendre un paramètre d'entrée de type `uint` et augmenter la valeur de la variable `x` de la valeur du paramètre d'entrée.
2. Make sure that x can only be increased.
3. The body of the function `increaseX` should be empty.

Tip: Use modifiers.