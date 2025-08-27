CODECOPY na one of the plenty opcodes wey EVM de run. Go check the complete list of opcodes for <a href="https://ethervm.io/" target="_blank">https://ethervm.io/</a> .

CODECOPY takes the **running code** (or part of it) and to copies it from the `calldata` to the `memory`.

The Solidity implementation na **codecopy(t, f, s)** - copy **s** bytes from code wey dey position **f** to memory wey dey position **t**.

Every contract wey dem deploy de use **CODECOPY**.
