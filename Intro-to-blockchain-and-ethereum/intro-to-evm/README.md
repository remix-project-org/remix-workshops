The **Ethereum Virtual Machine (EVM)** is the engine that turns transactions into changes on Ethereum and other EVM-compatible chains.

It’s not one server. It’s a set of rules (a specification). Every node follows the same rules so that, with the same inputs, they all get the same result. The EVM defines what a smart contract can do, how data is stored, what operations exist, and how much those operations cost.

## How the EVM works

A user signs a transaction in a wallet and sends it to the network. A node checks that the signature is valid, that the account’s order number (nonce) is correct, and that the account can afford the maximum cost. The node then hands the transaction to the EVM with a gas limit.

Gas is the fee paid for computational work on Ethereum. It is paid in ETH (usually quoted in gwei), and a gas limit is the maximum number of gas units you allow the transaction to consume.

The EVM runs the contract code step by step. Each step uses some gas. If execution succeeds, the contract’s stored data (state) is updated and the transaction can emit events that your app can later read. If execution fails, the state changes are rolled back, but the gas used up to that point will not be refunded.

When it’s done, the node returns a receipt. The receipt says whether the transaction succeeded, how much gas it used, which events were emitted, and, if you deployed a contract, the new contract address.

## Further Reading

- [The Ethereum virtual machine](https://ethereum.org/developers/docs/evm/).
- [The Ethereum Yellow Paper](https://ethereum.github.io/yellowpaper/paper.pdf).