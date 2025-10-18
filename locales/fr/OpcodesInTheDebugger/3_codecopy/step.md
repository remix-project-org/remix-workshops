CODECOPY is one of the many opcodes run by the EVM. Consultez la liste complète des opcodes sur <0>https://ethervm.io/</0> .

CODECOPY takes the **running code** (or part of it) and to copies it from the `calldata` to the `memory`.

The solidity implementation is: **codecopy(t, f, s)** - copy **s** bytes from code at position **f** to memory at position **t**.

Every contract deployment uses **CODECOPY**.
