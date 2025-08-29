In Solidity, we can define custom data types in the form of _structs_. Structs are a collection of variables that can consist of different data types.

### Defining structs

Nous définissons une structure en utilisant le mot-clé `struct` et un nom (ligne 5). Inside curly braces, we can define our struct’s members, which consist of the variable names and their data types.

### Initialisation des structures

Il existe différentes façons d'initialiser une structure.

Positional parameters: We can provide the name of the struct and the values of its members as parameters in parentheses (line 16).

Key-value mapping: We provide the name of the struct and the keys and values as a mapping inside curly braces (line 19).

Initialiser et mettre à jour une structure : Nous initialisons d'abord une structure vide, puis mettons à jour son membre en lui attribuant une nouvelle valeur (ligne 23).

### Accessing structs

To access a member of a struct we can use the dot operator (line 33).

### Mise à jour des structures

Pour mettre à jour le membre d'une structure, nous utilisons également l'opérateur de point et lui attribuons une nouvelle valeur (lignes 39 et 45).

<0>Regardez un tutoriel vidéo sur les structures</0>.

## ⭐️ Affectation

Create a function `remove` that takes a `uint` as a parameter and deletes a struct member with the given index in the `todos` mapping.