Dans Solidity _enums_ sont des types de données personnalisés constitués d'un ensemble limité de valeurs constantes. We use enums when our variables should only get assigned a value from a predefined set of values.

In this contract, the state variable `status` can get assigned a value from the limited set of provided values of the enum `Status` representing the various states of a shipping status.

### Defining enums

We define an enum with the enum keyword, followed by the name of the custom type we want to create (line 6). Inside the curly braces, we define all available members of the enum.

### Initializing an enum variable

We can initialize a new variable of an enum type by providing the name of the enum, the visibility, and the name of the variable (line 16). Upon its initialization, the variable will be assigned the value of the first member of the enum, in this case, Pending (line 7).

Even though enum members are named when you define them, they are stored as unsigned integers, not strings. They are numbered in the order that they were defined, the first member starting at 0. La valeur initiale du statut, dans ce cas, est 0.

### Accessing an enum value

To access the enum value of a variable, we simply need to provide the name of the variable that is storing the value (line 25).

### Updating an enum value

We can update the enum value of a variable by assigning it the `uint` representing the enum member (line 30). Shipped would be 1 in this example. Another way to update the value is using the dot operator by providing the name of the enum and its member (line 35).

### Suppression d'une valeur d'énumération

We can use the delete operator to delete the enum value of the variable, which means as for arrays and mappings, to set the default value to 0.

<0>Regardez un tutoriel vidéo sur Enums</0>.

## ⭐️ Assignment

1. Define an enum type called `Size` with the members `S`, `M`, and `L`.
2. Initialisez la variable `sizes` du type d'énumératage `Size`.
3. Create a getter function `getSize()` that returns the value of the variable `sizes`.