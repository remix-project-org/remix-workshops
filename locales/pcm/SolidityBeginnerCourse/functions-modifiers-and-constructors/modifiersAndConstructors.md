For dis section, we go learn how dey they modify behavior for function and how to run contract initialization code.

### De function Modiifier

_De function Modiifier_ fit change the behaviour of a function. For example, dem dey check for one condition before dem execute any function make e restrict access or validate inputs.

Dis first part of dis contract na to change ownership of de contract. Ownership wey dey for dis contract is expressed by the value of the state variable `owber` wey dey for the type `address` ( line 7).

De function `changeOwner` (line 33) fit change dis ownership. E dey take input parameter wey get the type `address` con give am value of the state variable `owner`.

But still, dis function fit no work for all conditions, e get two modifiers, `onlyOwner` and `validAddress`.

Make we see the `onlyOwner` first (line 18).
Function modifiers dey defined with the `modifier` keyword and e unique name; dey fit get parameters too.

The underscore `_` (line 23) dey used for inside modifiers to take represent di remaining part of di code wey go dey executed for di body of the modified function.
The code wey you put before the underscore for the modifier go run before the code wey dey inside the modified function. The code wey dey after the undercore go execute after the code wey dey the body of the function wey dem modify.

For dis case, the `require` function (line 19) go check if the address wey dey execute the contract dey the same as the value wey dey stored for the variable `owner`. If na am, the remaining code go execute, or else e go bring error.

You fit know more about `assert` and `require` for the <a href="https://docs.soliditylang.org/en/latest/control-structures.html#error-handling-assert-require-revert-and-exceptions" target="_blank">Solidity documentation</a>, e dey used to check for conditions con show error if dem no dey met.

The `validAddress` modifier (line 28) get one parameter of type `address` e go check if the provided address dey valid. If e dey, e go continue dey execute the code.

### Constructor

Constructor function go execute as you dey create any contract. You fit use am do contract initialization code. The constructor fit get parameters wey dey very useful when you no know some kind initialization values before you deploy the contract.

You fit declare constructor by using the `constructor` keyword. The constructor wey dey dis contract (line 11) dey set the first value of the owner variable as you dey make the contract.

<a href="https://www.youtube.com/watch?v=b6FBWsz7VaI" target="_blank">Watch this video tutorial on Function Modifiers</a>.

## ⭐️ homework

1. Create one new function, `increaseX` for inside the contract. The function suppose take input parameter wey get type `uint` con increase the number for the variable `x` by the value of the input parameter.
2. Dey sure say na only increase the x fit increase.
3. The `increaseX` function body suppose dey empty.

Tip: try use modifiers.