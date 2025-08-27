For Solidity, variable fit dey for different kain location: _memory_ wey be temporary, _storage_ wey permanent for blockchain, and _calldata_ wey hold the input wey no fit change.

As we don talk before, value type variable dey keep hin own copy of value, while reference type variable (array, struct, mapping) dey only store location(position) of di value.

If we use reference type for function, we gats talk where we wan store the value for di data. Na Data location dey determine money wey you go pay because you use di function; you go pay small money if you use reference create ccopy.

### Main store house

Value wey you store for _storage_ go dey for blockchain forever na why e cost to use am.

For dis contract, state variables dem `arr`, `map`, and `myStructs` (lines 5, 6, and 10) dey inside storage. Na for storage na hin dem dey always keep State variables.

### Short time store

Value wey you store for _memory_ no dey tey for the blockchain. Na when you dey use external function na hin e go dey after dat one e go delete. E no cost like value wey you keep for _storage_.

For dis contract, di local variable `myMemstruct` (line 19), and parameter `_arr` (line 31) dey for inside memory. Function parameters data location gats be either _memory_ or _calldata_.

### Store house for di function memory

_Calldata_ dey keep function values. E be like _memory_ because _calldata_ sef dey only keep am while you dey do external function. No be everything e use take be like _memory_ because e no be like memory wey you fit change value wey dem keep for there. Na calldata cheap pass for data location.

For dis contract, `parameter _`arr`(line 35) data location na for *calldata*. If we wan give new value to th first element for the lisdt`_arr`, we fit do am for `function g`(line 31) but no be as`function h`(line 35). Na because`_arr`for`function g`dey for *memory* but *function h* dey`calldata\`.

## Value wey you give variable

### Memory to memory

Assignments from _memory_ to _memory_ create references instead of copies. If you change the value in one variable, the value of all other variables that reference the same data will be changed.

If we were to create a new struct `myMemStruct2` with the data location _memory_ inside the `function f` (line 12) and assign it the value of `myMemStruct` (line 19), any change to `myMemStruct2` would also change the value of `myMemStruct`.

### Storage to local storage

Assignments from _storage_ to _local storage_ also create references, not copies.

If we change the value of the local variable `myStruct` (line 17), the value of our state variable `myStructs` (line 10) changes as well.

## Storage and memory/calldata

Assignments between _storage_ and _memory_ (or _calldata_) create independent copies, not references.

If we were to create a new struct `myMemStruct3` with the data location _memory_ inside the `function f` (line 12) and assign it the value of `myStruct`, changes in `myMemStruct3` would not affect the values stored in the mapping `myStructs` (line 10).

As we said in the beginning, when creating contracts we have to be mindful of gas costs. Therefore, we need to use data locations that require the lowest amount of gas possible.

## ⭐️ Assignment

1. Change the value of the `myStruct` member `foo`, inside the `function f`, to 4.
2. Create a new struct `myMemStruct2` with the data location _memory_ inside the `function f` and assign it the value of `myMemStruct`. Change the value of the `myMemStruct2` member `foo` to 1.
3. Create a new struct `myMemStruct3` with the data location _memory_ inside the `function f` and assign it the value of `myStruct`. Change the value of the `myMemStruct3` member `foo` to 3.
4. Let the function f return `myStruct`, `myMemStruct2`, and `myMemStruct3`.

Tip: Make sure to create the correct return types for the function `f`.