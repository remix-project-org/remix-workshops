Dans les sections suivantes, nous examinerons les structures de données que nous pouvons utiliser pour organiser et stocker nos données dans Solidity.

_Maries_, _mappages_ et _structs_ sont tous des _types de référence_. Contrairement aux types de _valeur_ (par exemple, les types de référence _booléens_ ou _entiers_) ne stockent pas directement leur valeur. Au lieu de cela, ils stockent l'emplacement où la valeur est stockée. Plusieurs variables de type de référence pourraient faire référence au même emplacement, et un changement dans une variable affecterait les autres, elles doivent donc être traitées avec soin.

Dans Solidity, un tableau stocke une liste ordonnée de valeurs du même type qui sont indexées numériquement.

Il existe deux types de tableaux, le temps de compilation _taille fixe_ et les _tableaux dynamiques_. Pour les tableaux de taille fixe, nous devons déclarer la taille du tableau avant qu'il ne soit compilé. La taille des tableaux dynamiques peut être modifiée après la compilation du contrat.

### Declaring arrays

Nous déclarons un tableau de taille fixe en fournissant son type, sa taille de tableau (sous forme d'entier entre crochets), sa visibilité et son nom (ligne 9).

Nous déclarons un tableau dynamique de la même manière. Cependant, nous ne fournissons pas de taille de tableau et laissons les parenthèses vides (ligne 6).

### Initializing arrays

We can initialize the elements of an array all at once (line 7), or initiate new elements one by one (arr[0] = 1;). If we declare an array, we automatically initialize its elements with the default value 0 (line 9).

### Accéder aux éléments du tableau

We access elements inside an array by providing the name of the array and the index in brackets (line 12).

### Ajout d'éléments de tableau

En utilisant la fonction membre `push()`, nous ajoutons un élément à la fin d'un tableau dynamique (ligne 25).

### Suppression des éléments du tableau

En utilisant la fonction membre `pop()`, nous supprimons le dernier élément d'un tableau dynamique (ligne 31).

Nous pouvons utiliser l'opérateur `delete` pour supprimer un élément avec un index spécifique d'un tableau (ligne 42).
When we remove an element with the `delete` operator all other elements stay the same, which means that the length of the array will stay the same. Cela créera un écart dans notre tableau.
If the order of the array is not important, then we can move the last element of the array to the place of the deleted element (line 46), or use a mapping. A mapping might be a better choice if we plan to remove elements in our data structure.

### Array length

Using the length member, we can read the number of elements that are stored in an array (line 35).

<a href="https://www.youtube.com/watch?v=vTxxCbwMPwo" target="_blank">Regardez un tutoriel vidéo sur Arrays</a>.

## ⭐️ Affectation

1. Initialiser un tableau public de taille fixe appelé `arr3` avec les valeurs 0, 1, 2. Faites la taille aussi petite que possible.
2. Change the `getArr()` function to return the value of `arr3`.