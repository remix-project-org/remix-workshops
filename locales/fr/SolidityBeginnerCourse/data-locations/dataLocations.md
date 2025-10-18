The values of variables in Solidity can be stored in different data locations: _memory_, _storage_, and _calldata_.

As we have discussed before, variables of the value type store an independent copy of a value, while variables of the reference type (array, struct, mapping) only store the location (reference) of the value.

If we use a reference type in a function, we have to specify in which data location their values are stored. Le prix de l'exécution de la fonction est influencé par l'emplacement des données ; la création de copies à partir de types de référence coûte de l'essence.

### Stockage

Values stored in _storage_ are stored permanently on the blockchain and, therefore, are expensive to use.

In this contract, the state variables `arr`, `map`, and `myStructs` (lines 5, 6, and 10) are stored in storage. State variables are always stored in storage.

### Memory

Les valeurs stockées en _mémoire_ ne sont stockées que temporairement et ne sont pas sur la blockchain. They only exist during the execution of an external function and are discarded afterward. They are cheaper to use than values stored in _storage_.

In this contract, the local variable `myMemstruct` (line 19), as well as the parameter `_arr` (line 31), are stored in memory. Function parameters need to have the data location _memory_ or _calldata_.

### Calldata

_Calldata_ stores function arguments. Comme _memory_, _calldata_ n'est stocké que temporairement pendant l'exécution d'une fonction externe. Contrairement aux valeurs stockées dans _memory_, les valeurs stockées dans _calldata_ ne peuvent pas être modifiées. Calldata is the cheapest data location to use.

In this contract, the parameter `_arr` (line 35) has the data location _calldata_. If we wanted to assign a new value to the first element of the array `_arr`, we could do that in the `function g` (line 31) but not in the `function h` (line 35). C'est parce que `_arr` dans `fonction g ` a l'emplacement des données _memory_ et _function h_ a l'emplacement des données `calldata`.

## Assignments

### Memory to memory

Les affectations de _mémoire_ à _mémoire_ créent des références au lieu de copies. If you change the value in one variable, the value of all other variables that reference the same data will be changed.

If we were to create a new struct `myMemStruct2` with the data location _memory_ inside the `function f` (line 12) and assign it the value of `myMemStruct` (line 19), any change to `myMemStruct2` would also change the value of `myMemStruct`.

### Storage to local storage

Assignments from _storage_ to _local storage_ also create references, not copies.

If we change the value of the local variable `myStruct` (line 17), the value of our state variable `myStructs` (line 10) changes as well.

## Storage and memory/calldata

Les affectations entre _storage_ et _memory_ (ou _calldata_) créent des copies indépendantes, pas des références.

Si nous devions créer une nouvelle structure `myMemStruct3` avec l'emplacement des données _memory_ à l'intérieur de la `fonction f` (ligne 12) et lui attribuer la valeur de `myStruct`, les modifications dans `myMemStruct3` n'affecteraient pas les valeurs stockées dans le mappage `myStructs` (ligne 10).

Comme nous l'avons dit au début, lors de la création de contrats, nous devons être conscients des coûts du gaz. Par conséquent, nous devons utiliser des emplacements de données qui nécessitent la quantité de gaz la plus faible possible.

## ⭐️ Affectation

1. Change the value of the `myStruct` member `foo`, inside the `function f`, to 4.
2. Create a new struct `myMemStruct2` with the data location _memory_ inside the `function f` and assign it the value of `myMemStruct`. Change the value of the `myMemStruct2` member `foo` to 1.
3. Créez une nouvelle structure `myMemStruct3` avec l'emplacement des données _memory_ à l'intérieur de la `fonction f` et attribuez-lui la valeur de `myStruct`. Change the value of the `myMemStruct3` member `foo` to 3.
4. Let the function f return `myStruct`, `myMemStruct2`, and `myMemStruct3`.

Conseil : Assurez-vous de créer les bons types de retour pour la fonction `f`.