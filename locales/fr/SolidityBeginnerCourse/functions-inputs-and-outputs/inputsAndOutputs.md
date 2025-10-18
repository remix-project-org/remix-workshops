In this section, we will learn more about the inputs and outputs of functions.

### Sorties nommées multiples

Functions can return multiple values that can be named and assigned to their name.

The `returnMany` function (line 6) shows how to return multiple values.
You will often return multiple values. It could be a function that collects outputs of various functions and returns them in a single function call for example.

La fonction `named` (ligne 19) montre comment nommer les valeurs de retour.
La dénomination des valeurs de retour contribue à la lisibilité de vos contrats. Named return values make it easier to keep track of the values and the order in which they are returned. You can also assign values to a name.

The `assigned` function (line 33) shows how to assign values to a name.
When you assign values to a name you can omit (leave out) the return statement and return them individually.

### Deconstructing Assignments

You can use deconstructing assignments to unpack values into distinct variables.

The `destructingAssigments` function (line 49) assigns the values of the `returnMany` function to the new local variables `i`, `b`, and `j` (line 60).

### Input and Output restrictions

Il existe quelques restrictions et meilleures pratiques pour les paramètres d'entrée et de sortie des fonctions contractuelles.

"\*[Mappings] ne peut pas être utilisé comme paramètres ou paramètres de retour des fonctions contractuelles qui sont visibles publiquement. \*"
Extrait de la <0>documentation Solidity</0>.

Les tableaux peuvent être utilisés comme paramètres, comme le montre la fonction `arrayInput` (ligne 71). Arrays can also be used as return parameters as shown in the function `arrayOutput` (line 76).

Vous devez être prudent avec les tableaux de taille arbitraire en raison de leur consommation de gaz. While a function using very large arrays as inputs might fail when the gas costs are too high, a function using a smaller array might still be able to execute.

<0>Regardez un tutoriel vidéo sur les sorties de fonction</0>.

## ⭐️ Affectation

Créez une nouvelle fonction appelée `returnTwo` qui renvoie les valeurs `-2` et `true` sans utiliser d'instruction return.