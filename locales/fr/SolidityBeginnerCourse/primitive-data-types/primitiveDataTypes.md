In this section, we will show you Solidity’s primitive data types, how to declare them, and their characteristics.

### bool

You can declare data a boolean type by using the keyword ‘bool’. Booleans can either have the value `true` or `false`.

### uint

We use  the keywords `uint` and `uint8` to `uint256` to declare an _unsigned integer type_ (they don’t have a sign, unlike -12, for example). Uints are integers that are positive or zero and range from 8 bits to 256 bits. The type `uint` is the same as `uint256`.

### int

We use the keywords `int` and `int8` to `int256` to declare an integer type. Integers can be positive, negative, or zero and range from 8 bits to 256 bits. Le type `int` est le même que `int256`.

### address

Les variables de type `adresse` ont une valeur de 20 octets, qui est la taille d'une adresse Ethereum. Il existe également un type spécial d'adresse Ethereum, « adresse payable », qui peut recevoir de l'éther du contrat.

All these data types have default values, as shown in the contract (line 29).

Vous pouvez en savoir plus sur ces types de données ainsi que sur les _nombres de points fixes_, les _matrices d'octets_, les _chaînes_ et plus encore dans la documentation <0>Solidité</0>.

Later in the course, we will look at data structures like **Mappings**, **Arrays**, **Enums**, and **Structs**.

<0>Regardez un tutoriel vidéo sur les types de données primitives</0>.

## ⭐️ Assignment

1. Create a new variable `newAddr` that is a `public` `address` and give it a value that is not the same as the available variable `addr`.
2. Create a `public` variable called `neg` that is a negative number, decide upon the type.
3. Create a new variable, `newU` that has the smallest `uint` size type and the smallest `uint` value and is `public`.

Conseil : Regardez l'autre adresse dans le contrat ou recherchez sur Internet une adresse Ethereum.
