Dis section we want learn more about di input and output of functions.

### Di multiple named outputs

Di function fit return multiple values wey fit define em name and assigned to their name.

Di return function (line 6) shows how to return multiple values.
U fit return multiple values. E fit be function wey collect outputs of different function and e return dem go single function call am example.

Di name function (line 19) shows how to name return values.
Name go return values help with di readability of ur contracts. Im name return value make am easier to keep track of di values and di order in which dem dey return. U fit assign values to name am.

Di assigned function (line 33) shows how to assign values to a name.
When u assign values to a name u fit omit (leave out) de return statement and return them individually.

### Di constructing assignment

U fit deconstruct assignment to unpack values into distinct variables.

Di destructing Assigment function (line 49) assigns the values of the `returnMany` function to the new local variables `i`, `b`, and `j` (line 60).

### De Input and Output restrictions

Dem get few restrictions and best practices fo di input and output parameters of contract functions.

"_[Mappings] cannot be used as parameters or return parameters of contract functions that are publicly visible._"
From the <a href="https://docs.soliditylang.org/en/latest/types.html#mapping-types" target="_blank">Solidity documentation</a>.

Arrays fit use parameters show am di function`arrayInput` (line 71). Arrays fit use am return parameters as dem show am for di function `arrayOutput` (line 76).

U gat dey caution with arrays of arbitrary size becuz of di gas consumption. While di function using very large arrays as na inputs fit fail when di gas don cost are too high a function wey dey use small small array fit execute.

<a href="https://www. youtube. com/watch? v=_5vGaqgzlG8" target="_blank">U go watch video tutorial wen u dey send Ether</a>.

## di ⭐️ Assignment

U go create new function call am`returnTwo` that returns the values `-2` and `true` without using a return statement.