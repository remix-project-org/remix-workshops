For the Solidity, _mappings_ na collection of key types and corresponding value type pairs

De biggest difference btw a mapping and array be say u no fit iterate over mappings. If we no know key we no go fit access e value. If we want know all of our data or iterate over am, we go use array.

If we want retrieve value wen base on a known key we fit use mapping (e.g addresses fit be used as keys. If we look up values with mapping e dey easier and cheaper pass iterating over arrays. If de arrays too large, de gas cost of iterating over am it fit become too high e fit cause the transaction to fail.

We fit store de keys of de mapping for array wey we fit iterate over.

### Creating mappings

Mappings dey declared with the syntax `mapping(KeyType => ValueType) VariableName`.
The key type fit be any inbuilt value type abi contract, but e no fit be reference type. The value type fit be any type at all.

For dis contract, we dey create public mapping `myMap` (line 6) wey dey associate the key type `address` go the value type `uint`.

### Accessing values

The syntax wey you go use interact with key-value pairs for mapping dey similar to the type for array.
To find the value wey dey together with one particular key, we go provide the name of the mapping and the key for brackets (line 11).

Different from arrays, we no go get error if we try access the value of any key wey never get set value yet. Anytime wey ee create mapping, all the possible key go dey mapped to 0 wey be the default value.

### Setting values

We fit set new value for any key as long say we provide the mapping name and key for bracket con give am new value (line 16).

### To dey commot values

We fit use the delete operator take delete the value wey dey associated with any key, wey go con set am go 0 wey be the default value. As we don see for the array section.

<a href="https://www.youtube.com/watch?v=tO3vVMCOts8" target="_blank">Watch this video tutorial on Mappings</a>.

## ⭐️ homework

1. Make one public mapping `balances`wey go join the key type `address` with the value type `uint`.
2. Change the get and remove function make e work with the mapping balances.
3. Change the function `set` to create a new entry to the balances mapping, where the key is the address of the parameter and the value is the balance associated with the address of the parameter.