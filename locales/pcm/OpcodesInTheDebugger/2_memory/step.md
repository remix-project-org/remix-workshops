Before we start, just quick reminder:

The runtime of the EVM has several kinds of memory:

- `calldata`: This one na the input wey dem give the transaction.
- `stack`: Normal Normal, this one na the list of values, each value get limited size (32 bytes).
- `memory`: Dem go use memory when the **kain** value wey dem dey store dey more complexed like array or mapping. This memory dey **temporary** and dem go **release** am at the end of the execution.
- `storage`: Na mapping be this, each value wey dem store go dey **persisted** and saved onchain.
