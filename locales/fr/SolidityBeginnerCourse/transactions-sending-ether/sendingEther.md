Dans cette section, nous allons apprendre comment un contrat peut envoyer et recevoir de l'éther.

### Envoi d'éther

We have three different options to transfer Ether: `transfer()`, `send()` and `call()`.

#### **transfer**

`<0>.transfer(uint256 amount)`

- `transfer()` throws an exception on failure
- Forwards a fixed 2300 gas stipend

An example of `transfer()` can be seen in the `SendEther` contract (line 35).
**`Transfer()` is not recommended to be used anymore.**

#### **send**

`<0>.send(uint256 amount) returns (bool)`

- `send()` renvoie faux en cas d'échec
- Avance une allocation de gaz fixe de 2300

An example of `send()` can be seen in the `SendEther` contract (line 41).
\*\*`Send()` n'est plus recommandé. \*\*

#### **call**

`<address>.call(bytes memory) returne (bool, bytes memory)`

- `call()` returns false on failure
- Forwards the maximum amount of gas, but this is adjustable

An example of `call()` can be seen in the `SendEther` contract (line 48).
`Call()` is currently recommended if you are transfering Ether.

The reason `transfer()` and `send()` were introduced was to guard against _reentry attacks_ by limiting the forwarded gas to 2300, which would be insufficient to make a reentrant call that can modify storage.

As we discussed in the last section, each operation on Ethereum has a specific cost associated with it. Certain operations have become more cost intensive over time, so the gas costs associated with them are also raised. When gas costs for operations are subject to change it is not good to use a hardcoded gas amount like transfer(), and send() do.

C'est pourquoi `call()` au lieu de `transfer()` est maintenant recommandé pour envoyer Ether.

Apprenez-en plus sur le sujet dans cet article de blog <a href="https://consensys.net/diligence/blog/2019/09/stop-using-soliditys-transfer-now/" target="_blank">Consensys</a>.

### Attaque de réentrée

A _reentrancy attack_ occurs when a function makes an external call to an untrusted contract and the attacker uses the contract to make recursive calls back to the original function before it finishes its execution. Through this method, the attacker can drain funds and manipulate data in unintended ways.

To guard against a _reentrancy attack_, all state changes should be made before calling an external contract. C'est ce qu'on appelle aussi le modèle <0>Checks-Effects-Interactions</0>.

Another way to prevent reentrancy is to use a _Reentrancy Guard_ that checks for such calls and rejects them. Vous pouvez voir un exemple de ceci dans le contrat dans notre section modificateur ou une version plus économe en gaz sur <0>Open Zepplin</0>.

### Receiving Ether

If we want to enable a contract to receive Ether without a function being called, we need to create a `receive` function (line 22) or a `fallback` function (line 25); otherwise, the Ether will be rejected, and the contract will throw an exception.

La fonction `receive` est exécutée sur les appels avec des données d'appel vides (par exemple, des transferts Ether simples via send() ou transfer()), tandis que la fonction de secours est exécutée sur les appels avec des données d'appel. If no receive function exists but a fallback function does, calls with empty calldata will also use the fallback function.

### Le modificateur de fonction payable

Le modificateur de fonction `payable` permet à une fonction de recevoir Ether.

The `receive` function (line 22) needs to be `payable`. If you delete the `payable` modifier you will get an error from the compiler. Si vous supprimez le modificateur `payable` de la fonction `fallback` (ligne 25), il se compilera, mais il ne pourra pas recevoir d'éther.
The functions `sendViaTransfer`, `sendViaSend`, and `sendViaCall` (lines 33, 38, and 45) also need to be `payable` in order to receive Ether.

### Adresse à payer

Solidity fait une distinction entre deux saveurs différentes du type de données d'adresse : adresse et adresse payable.

`address`: Holds a 20-byte value.
`address payable`: Holds a 20-byte value and can receive Ether via its members: transfer and send.

If you change the parameter type for the functions `sendViaTransfer` and `sendViaSend` (line 33 and 38) from `payable address` to `address`, you won’t be able to use `transfer()` (line 35) or `send()` (line 41).

<0>Regardez un tutoriel vidéo sur l'envoi d'éther</0>.

## ⭐️ Affectation

Build a charity contract that receives Ether that can be withdrawn by a beneficiary.

1. Create a contract called `Charity`.
2. Add a public state variable called `owner` of the type address.
3. Create a donate function that is public and payable without any parameters or function code.
4. Créez une fonction de retrait qui est publique et envoie le solde total du contrat à l'adresse `propriétaire`.

Tip: Test your contract by deploying it from one account and then sending Ether to it from another account. Then execute the withdraw function.