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

### De Receiving Ether

If we wan enable contract to te receive Ether witout function being called, we go need make we create receive function (line 22) or fall go back function (line 25) otherwise, de Ether go dey rejected, and de contract go throw expection.

De receive function dey executed on call wey get empty callday (e.g.plain Ether transfer via send()or transfer()), while de fallback function dey executed for calls wit calldata. If any receive function no exist but fallback function dey do am im dey call wit empty calldata go also dey use de function wey dey fallback.

### De payable function wey dey modify

De payable function wey dey modify dey allow functon to dey receive Ether.

De receiver function (line 22) need to dey payable. If u don deletede delete de payable modifier u go get error from de compiler. If u don delete de payable modifier from de fallback function (line 25) im go co, pile, but im no go fit able receive Ether.
De functions sendviatransfer sendviasend and sendviacall (lines 33 38and 45) go also need to dey payable in order make im receive Ether.

### Address wey dey payable

De solidity go make distinction between two different flavours of de address data type address and address wey dey payable.

D address dey hold 20-byte value.
De address wey dey payable dey hold 20-byte value and im go still receive Ether via its members transfer and go send.

If u fit change de parameter type for de function sendViaTransfer and sendViaSend (line 33 and38) from address to address u no go fit use transfer() (line 35) or send() (line 41).

<a href="https://www.youtube.com/watch?v=_5vGaqgzlG8" target="_blank">U go watch video tutorial wen u dey send Ether</a>.

## De Assignment

U go build charity contact wey dey recieve Ether wey u fit witdraw by beneficiary.

1. U go create contact wey dem dey call charity.
2. U go add public state variable wey dem dey call owner of de type of addresses.
3. U go create donate function wey dey public wey dey payable witout any thing wey dey block am or code wey get function.
4. U go create witdraw function wey be public wey go send de total balance of de contract de person wey get address.

Tip: U go test ur contract wen u dey develop am fromone account and den we go send Ether to it from account wey no be how own. Den u go execute de witdrawn function.