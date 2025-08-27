Dem get three different types of variables for solidity _State Variables_, _Local Variables_, and _Global Variables_.

## na 1. De State Variables

_State Variables_ dey stored for di contract _storage_ and thereby on the blockchain. They don declared for inside say di contract but outside di function.
Dis contract get two state variables, using di string `text`(line 6) and the uint `num` (line 7).

## dis na 2. Di local variables

_di local variables_dem store am for di _memory_ and thier values are only accessible within di function dem don define in. Dis local Variables dem no stored am for di blockchain.
Dis contract di uint `i` (line 11) is a local variable.

## na 3. Di Global Variables

_Global Variables_, also called _Special Variables_, exist in de global namespace. Dem no need declared but associated with ur contract.
Global variables dem use am retrieve information about di blockchain, particular addresses, contract and transactions.

For dis side we fit use `block.timestamp` (line 14) to get a Unix timestamp of when the current block was generated and `msg.sender` (line 15) to get di caller of di contract function’s address.

One list of all the plenty Global variables go dey availaible <a href="https://docs.soliditylang.org/en/latest/cheatsheet.html?highlight=Variables#global-variables" target="_blank">Solidity documentation</a>.

U go waatch video tutorialsfor <a href="https://docs.soliditylang.org/en/latest/cheatsheet.html?highlight=Variables#global-variables" target="_blank">State Variables</0>, <1>Local Variables</1>, and <2>Global Variables</2>.

## De Assignment

1. How to te new public state variable wey dem dey blockNumber.
2. Inside de functoin doSomething() assign de value of de book wey dey current block number to de state variable blockNumber.

Tip Look into de global variables section of de solidify documents to te find out how to te read de current number wey block.
