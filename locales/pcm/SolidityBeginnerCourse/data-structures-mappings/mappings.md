For the Solidity, _mappings_ na collection of key types and corresponding value type pairs

De biggest difference btw a mapping and array be say u no fit iterate over mappings. If we no know key we no go fit access e value. If we want know all of our data or iterate over am, we go use array.

If we want retrieve value wen base on a known key we fit use mapping (e.g addresses fit be used as keys. If we look up values with mapping e dey easier and cheaper pass iterating over arrays. If de arrays too large, de gas cost of iterating over am it fit become too high e fit cause the transaction to fail.

We fit store de keys of de mapping for array wey we fit iterate over.

### Creating mappings

Mappings are declared with the syntax `mapping(KeyType => ValueType) VariableName`.
The key type can be any built-in value type or any contract, but not a reference type. The value type can be of any type.

In this contract, we are creating the public mapping `myMap` (line 6) that associates the key type `address` with the value type `uint`.

### Accessing values

The syntax for interacting with key-value pairs of mappings is similar to that of arrays.
To find the value associated with a specific key, we provide the name of the mapping and the key in brackets (line 11).

In contrast to arrays, we won't get an error if we try to access the value of a key whose value has not been set yet. When we create a mapping, every possible key is mapped to the default value 0.

### Setting values

We set a new value for a key by providing the mapping’s name and key in brackets and assigning it a new value (line 16).

### Removing values

We can use the delete operator to delete a value associated with a key, which will set it to the default value of 0. As we have seen in the arrays section.

<a href="https://www.youtube.com/watch?v=tO3vVMCOts8" target="_blank">Watch a video tutorial on Mappings</a>.

## ⭐️ Assignment

1. Create a public mapping `balances` that associates the key type `address` with the value type `uint`.
2. Change the functions `get` and `remove` to work with the mapping balances.
3. Change the function `set` to create a new entry to the balances mapping, where the key is the address of the parameter and the value is the balance associated with the address of the parameter.