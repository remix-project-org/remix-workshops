There are three different types of variables in Solidity: _State Variables_, _Local Variables_, and _Global Variables_.

## 1. State Variables

_Les variables d'état_ sont stockées dans le contrat _stockage_ et donc sur la blockchain. They are declared inside the contract but outside the function.
This contract has two state variables, the string `text`(line 6) and the uint `num` (line 7).

## 2. Local Variables

_Local Variables_ are stored in the _memory_ and their values are only accessible within the function they are defined in. Local Variables are not stored on the blockchain.
In this contract, the uint `i` (line 11) is a local variable.

## 3. Global Variables

_Global Variables_, also called _Special Variables_, exist in the global namespace. Ils n'ont pas besoin d'être déclarés, mais peuvent être consultés à partir de votre contrat.
Global Variables are used to retrieve information about the blockchain, particular addresses, contracts, and transactions.

In this example, we use `block.timestamp` (line 14) to get a Unix timestamp of when the current block was generated and `msg.sender` (line 15) to get the caller of the contract function’s address.

Une liste de toutes les variables globales est disponible dans la <a href="https://www.youtube.com/watch?v=hl692-xJPUQ" target="_blank">documentation Solidity</a>.

Regardez des tutoriels vidéo sur <0>Variables d'état</0>, <1>Variables locales</1> et <2>Variables globales</2>.

## ⭐️ Affectation

1. Create a new public state variable called `blockNumber`.
2. Inside the function `doSomething()`, assign the value of the current block number to the state variable `blockNumber`.

Tip: Look into the global variables section of the Solidity documentation to find out how to read the current block number.
