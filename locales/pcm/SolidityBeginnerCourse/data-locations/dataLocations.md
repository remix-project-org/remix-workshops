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

Value wey you give from _memory_ to _memory_ no dey copy but e dey reference. If you change one variable value, the value for di remaining variable wey reference di same data go change.

If we create new struct `myMemStruct2` wit dat location _memory_ for inside `function f` (line 12) kon give am di value of 'myMemStruct`(line 19), if I change anything for`myMemStruct2`e go change`myMemStruct\` value.

### Storage to loca storage

Value wey you give from _storage_ to _local storage_ sef dey create reference, no be copy.

If we change value of local variable `myStruct` (line 17), di value of state variable `myStructs` (line 10) sef go change.

## Storage and memory/calldata

Value wey variable carry for _storage_ and _memory_ (or _calldata_) get seperate copies no be reference.

If we make new struct `myMemStruct3` wit data location _memory_ inside `function f` (line 12) kon give am value of `myStruct` e no affect value wey dey for mapping `myStructs` (line 10).

As we don talk as we dey start, we gats dey think of transaction money as we dey create contract. So we gats use data location wey no too need gas wey cost.

## When you give variable value

1. Change value of `mystruct` member `foo`, inside `function f`, to 4.
2. Create new struct `myMemstruct2` wit data location inside `function f` kon give am value of `myMemStruct`. Change value of `myMemStruct2` member `foo` to 1.
3. Create new struct `myMemStruct3` wey di data location na _memory_ inside `function f` kon give am value of `myStruct`. Change the value of `myMemStruct3` member `foo` to 3.
4. Make function f show the value for `myStruct`, `myMemStruct`, and `myMemStruct3`.

Small advice: No forget make correct return types for di function `f`.