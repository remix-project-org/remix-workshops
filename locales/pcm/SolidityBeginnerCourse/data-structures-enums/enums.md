For Solidity enums na custom data types wey get limited set of constant values. We go use enums if de variables go get assigned a value from a predefined set of values.

For dis contract, the state variable `status` fit get assigned a value from de limited set of provided values of the enum `Status` wey dey represent de various states of de shipping status.

### Defining enums

We fit define evum with de enum keyboard, wet follow de name of de custom type we wan create (line 6). For inside de curly braces, we fit define all available members of de enum.

### Initializing enum variable

We fit initialize new variable of de enum typeif we provide de name of de enum, de visibility, and de name of the variable (line 16). Upon de initialization, de variable go assign the value of the first member of the enum, for this case, Pending (line 7).

Even if enum members don get names when u define dem, dey fit store as unsigned integers, not strings. Dey they number then for order wey they define, de first number start for 0. For the initial value of de status, for dis case na 0.

### Access de enum value

If we want access the enum value of de variable, we go simply need to provide de name for de variable wey dey store de value(line 25).

### Update de enum value

We fit update de enum value of de variable if we assign e `unit` con represent de enum member (line 30). We go use shipped as 1 for dis example. Another way to update de value na to use dot operator to provide de name of de enum and w member (line 35).

### Remove de enum value

We fit use de delete operator to delete de enum value of de variable, which mena say as for arrays and mappings, we go set de default value to 0.

<a href="https://www.youtube.com/watch?v=yJbx07N15j0" target="_blank">Make u watch video tutorial on Enums</a>.

##

1. Define de enum type called `Size` with the members `S`, `M` and `L`.
2. Initialize the variable `sizes` of the enum type `Size`.
3. Create a getter function `getSize()` that returns the value of the variable `sizes`.