For di next part, we go look the structure of data wey we fit use arrange and store our data for Solidity.

_Arrays_, _mappings_ and _structs_ na all _reference type_. E no be like _value types_(e.g. _booleans_ or _integers_) reference types dem no dey store value direct. Instead, e go store the place wey the value dey. Plenty reference type variable fit dey show the same location, make one change for variable cause wahala for di rest, so dem suppose dey handle them well well.

For Solidity, array dey store arranged list of values wey be di same type wey dem postion wit number.

Na two types of array dey, compile-time _fixed-size_ and _dynamic arrays_. For fixed-size arrays, we gats talk how the array take big abi small before e go compile am. Di size of dynamic arrays fit change after the contract don dey compiled.

### How to take announce say list go dey

We dey announce fixed-size array if we talk hin type, size (as integer for square braket), who fit see am, and name (Line 9).

Na the same way we dey let computer sabi say dynamic array go dey. But we no dey talk array size kon leave bracket empty (line 6).

### How to take put arrays

We fit put all the element of array one time (line 7), abi make we dey put am one by one(arr[0] = 1;). If we announce array, we go put all the elements like that with value 0 (line 9).

### How you fit pick items for array

We fit pick item wey dey inside array if we write di name of di array and the position number for bracket (line 12).

### How you fit put things for inside array

If you use `push()` member function, you go put item for the last side of dynamic array (line 25).

### How you fit comot thing for inside array

If we use `pop()` member function, we fit comot the last element of dynamic array (line 31).

We fit use `delete` operator take comot lement with specific position number for any array (line 42).
If we use `delete` operator take comot something all di remaining things no go change, e mean say how di array take long no go change. E go put space for our array.
If how di array take arrange no dey important, we fit shift di last thing for the array go where we comot something now (line 46), abi make we carry each one do di same thing for am. E go beta if we carry each one do the same thing for am if we wan comot our items for our data shape.

### How di list take long

If we use the counter wey dey tell us how di list take long, we fit read the number of any itemwey dey inside the list (line 35).

<a href="https://www.youtube.com/watch?v=vTxxCbwMPwo" target="_blank"> Watch video wey go explain array</a>.

## ⭐️ Home work

1. Do public fixed-size array kon name am `arr3` wit values 0, 1, 2. Make e small as e fit be.
2. Change di `getArr()` function make e tell the value of `arr3`.