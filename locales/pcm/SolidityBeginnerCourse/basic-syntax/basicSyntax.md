For this section, we go create our first _smart contract_. This contract only consists of a string that holds the value "Hello World!".

Inside the first line, we suppose specify the license wey we wan use. You can find a comprehensive list of licenses here: <a href="https://spdx.org/licenses/" target="_blank">https://spdx.org/licenses/</a>.

As we dey use `pragma` keyword (line 3), we specify the Solidity version wey we want make the compiler use. For this matter, e suppose dey equal to and greater than `0.8.3` but e go small pass 0.9.0.

We dey define contract with the keyword `contract` and we go give am name. for this matter, `HelloWorld` (line 5).

Inside our contract, we define _state variable_ `greet` wey dey hold the the string `"Hello World!"` (line 6).

Solidity na statically typed language, and this one mean say you must to specify the kain variable when you declare am. For this matter, `greet` na `string`.

We also define the _visibility_ of the variable wey de specify from where you fit access am. For this matter, na `public` variable wey you fit access from inside and outside the contract.

Don't worry if you didn't understand some concepts like _visibility_, _data types_, or _state variables_. We go look into them inside all this sections.

Make persin fit understand the code, we go. link inside all this sections to video tutorials from <a href="https://www.youtube.com/channel/UCJWh7F3AFyQ_x01VKzr9eyA" target="_blank">creator</a> of Solidity by Example contracts.

<a href="https://www.youtube.com/watch?v=g_t0Td4Kr6M" target="_blank">Watch video tutorial on top Basic syntax</a>.

## ⭐Carry this work go do

1. Delete the HelloWorld contract and its content.
2. Create a new contract named "MyContract".
3. The contract should have a public state variable called "name" of the type string.
4. Assign the value "Alice" to your new variable.
