# Di Proxy Contract AKA de Dispatcher

## Why?

Dis kind pattern wey dem dey used mainly in **library development**.

E fit help de ff ways:

- **Save gas cost at deployment time**
  de purpose of a high gas cost is to discourage the operations that cost a lot for their execution and to fit encourage optimized code.

- Di proxy contract dey useful when a lot of instance of di same conntract need dey deployed becuz dem reduce di duplicatiions in di deployment.

- **Avoid code repetition in the blockchain.**
  Heavy computations dey very expensive becuz every node go need to perform them, this is of course slowing the network.

- **Develop upgradable(versioned) contracts**
  When de contract is deployed, it’s immutable. With re-designing di code into different contracts if fit dey possible to allow logic upgrades when di storage di same.

## Di Example of gas cost

To store contract code at creation time fit cost:

- di 200 \* max_byte_code_length gas
- di 200 \* 24576 = 49152004915200 \* 10 gwei = 49152000 gwei = 0.049152 ether = 9 EUR

u fit see https://github.com/ethereum/EIPs/blob/master/EIPS/eip-170.md for more info on max_byte_code_length.
