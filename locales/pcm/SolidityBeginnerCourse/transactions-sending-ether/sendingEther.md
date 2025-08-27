Inside dis section, we go learn how contract fit send and receive Ether.

### To send Ether

We get three different options to transfer Ether: `transfer()`, `send()` and `call()`.

#### **transfer**

`<address payable>.transfer(uint256 amount)`

- `transfer()` e dey throw exception ontop failure
- E dey forward a fixed 2300 gas stipend

Yu fit see example of `transfer()` inside di `SendEther` contract (line 35).
**`Transfer()` no dey recommended to use like before again.**

#### **send**

`<address payable>.send(uint256 amount) returns (bool)`

- `send()` e dey return false if e fail
- E dey forward a fixed 2300 gas stipend

Yu fit see example of `send()` inside the `SendEther` contract (line 41).
**`Send()` no dey recommended to dey use like before.**

#### **call**

`<address>.call(bytes memory) dey return (bool, bytes memory)`

- `call()` e dey return false if e fail
- E dey forward d maximum amount of gas, but dem fit adjust am

Yu fit see example of `call()` inside di `SendEther` contract (line 48).
`Call()` no dey recommended like before again if you dey transfer Ether.

Di reason dem inrtoduce `transfer()` and `send()` na to guard against _reentry attacks_ by limiting di forwarded gas to 2300, wey go con dey insufficient to make a reentrant call wey fit modify storage.

As we don discuss for di last section, each operation ontop Ethereum get specific cost wey dem associate with am. Certain operations don dey more expensive with time, so the gas costs wey dey associated with them are don also increase. When dem change gas costs for operations e no good to use hardcoded gas amount like transfer(), and send() do am.

Na why `call()` instead of `transfer()` dey recommended now to dey send Ether.

Yu fit Learn more about d subject inside here <a href="https://consensys.net/diligence/blog/2019/09/stop-using-soliditys-transfer-now/" target="_blank">Consensys blog post</a>.

### Reentrancy attack

A _reentrancy attack_ dey occur when function make external call go meet untrusted contract nd the attacker con use di contract make recursive calls back go di original function before e finish hin execution. With this kind method, the attacker fit drain funds and manipulate data for unintended ways.

To fit guide against a _reentrancy attack_, do all state changes before u call an external contract. Dem dey also call am <a href="https://docs.soliditylang.org/en/latest/security-considerations.html#re-entrancy" target="_blank">Checks-Effects-Interactions</a> pattern.

Another way to prevent reentrancy na to use a _Reentrancy Guard_ wey go dey check for dat kind calls dey reject them. You fit see hin example inside the contract for our modifier section abi a more gas-efficient version ontop <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/security/ReentrancyGuard.sol" target="_blank">Open Zepplin</a>.

### Receiving Ether

If we want to enable a contract to receive Ether without a function being called, we need to create a `receive` function (line 22) or a `fallback` function (line 25); otherwise, the Ether will be rejected, and the contract will throw an exception.

The `receive` function is executed on calls with empty calldata (e.g. plain Ether transfers via send() or transfer()), while the fallback function is executed on calls with calldata. If no receive function exists but a fallback function does, calls with empty calldata will also use the fallback function.

### Payable function modifier

The `payable` function modifier allows a function to receive Ether.

The `receive` function (line 22) needs to be `payable`. If you delete the `payable` modifier you will get an error from the compiler. If you delete the `payable` modifier from the `fallback` function (line 25) it will compile, but it won’t be able to receive Ether.
The functions `sendViaTransfer`, `sendViaSend`, and `sendViaCall` (lines 33, 38, and 45) also need to be `payable` in order to receive Ether.

### Payable address

Solidity makes a distinction between two different flavors of the address data type: address and address payable.

`address`: Holds a 20-byte value.
`address payable`: Holds a 20-byte value and can receive Ether via its members: transfer and send.

If you change the parameter type for the functions `sendViaTransfer` and `sendViaSend` (line 33 and 38) from `payable address` to `address`, you won’t be able to use `transfer()` (line 35) or `send()` (line 41).

<a href="https://www.youtube.com/watch?v=_5vGaqgzlG8" target="_blank">Watch a video tutorial on Sending Ether</a>.

## ⭐️ Assignment

Build a charity contract that receives Ether that can be withdrawn by a beneficiary.

1. Create a contract called `Charity`.
2. Add a public state variable called `owner` of the type address.
3. Create a donate function that is public and payable without any parameters or function code.
4. Create a withdraw function that is public and sends the total balance of the contract to the `owner` address.

Tip: Test your contract by deploying it from one account and then sending Ether to it from another account. Then execute the withdraw function.