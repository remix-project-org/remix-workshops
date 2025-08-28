The goal here na to store the code inside the blockchain. The EVM need to tell the client (get, parity) wey dey part of the **call data** to store.   For dis step, we go save the contract MINUS the constructor because e go get implemented 1 time con MINUS de input parameter which no need to dey store am.

`CODECOPY` na the first step: it dey copy the bytecode to memory, den de Ethereum client go fit consume am.  Di MUNCH!

U go wait first... before the client go fit **MUNCH** bytecode, it go need instruction - an opcode to tell am to MUNCH. `RETURN` na the opcode!

As e state for the general spec, for di end of the contract creation, di client(geth, parity) go take the targeted value by di opcode `RETURN` and **persists** am con make am part of di deployed bytecode.

Once u don dey the `CODECOPY`, look di top 3 items for the **stack**:

0: 0x0000000000000000000000000000000000000000000000000000000000000000`
`1: 0x0000000000000000000000000000000000000000000000000000000000000055`
`2: 0x000000000000000000000000000000000000000000000000000000000000003e\`

_for ur stack- `1` & `2` fit be slightly different.  The difference fit be different compiler version._

**Na this be parameters for `CODECOPY`.**

Remember: _codecopy(t, f, s)_ - copy **s** bytes from code at position **f** to memory at position **t**

0 na be the offset where di copied code should be placed in the memory. For this example (all zeros) Dem dey copy the code to the beginning of the memory. (**t**)
`1` na the offset wey dey **calldata** where to copy from (**f**)
`2` number of bytes wey we go copy - (**s**)

After u don execute the `CODECOPY`, (click the _step into_ button) the copied code go be:
`0x6080604052600080fdfea265627a7a7231582029bb0975555a15a155e2cf28e025c8d492f0613bfb5cbf96399f6dbd4ea6fc9164736f6c63430005110032` in memory.  **I go call this value as (X)**.

Make we look at the debugger's **Memory** panel.
The 0x number wey i give for up no be wetin u go see for the **Memory** panel -wetin u go see na:
0x0: 6080604052600080fdfea265627a7a72 ????R??????ebzzr
0x10: 31582029bb0975555a15a155e2cf28e0 1X ?? uUZ??U????
0x20: 25c8d492f0613bfb5cbf96399f6dbd4e ?????a?????9?m?N
0x30: a6fc9164736f6c634300051100320000 ???dsolcC????2??
0x40: 00000000000000000000000000000000 ????????????????
0x50: 000000000000000000000000000000a0 ???????????????
0x60: 00000000000000000000000000000000 ????????????????
0x70: 00000000000000000000000000000000 ????????????????
0x80: 00000000000000000000000000000000 ????????????????
0x90: 00000000000000000000000000000002 ????????????????

De `0x0`, `0x10`, etc na de position. Di next number na di bytecode for dat position.  E dey followed by question marks and some kind random letters & numbers.  Na **Remix**'s attempt to fit convert dis tin into string.

So if we glue di first four section of bytecode togeda we no get
**0x6080604052600080fdfea265627a7a7231582029bb0975555a15a155e2cf28e0a6fc9164736f6c63430005110032**  De last section - `0x90` get 2 wey be say na wetin I put for constructor parameters.

The input data from the **Call Data** panel is:
`0x6080604052348015600f57600080fd5b506040516093380380609383398181016040526020811015602f57600080fd5b81019080805190602001909291905050508060008190555050603e8060556000396000f3fe6080604052600080fdfea265627a7a7231582029bb0975555a15a155e2cf28e025c8d492f0613bfb5cbf96399f6dbd4ea6fc9164736f6c634300051100320000000000000000000000000000000000000000000000000000000000000002`
**I go dey call dis value as (Y).**

E show us say `(X)` na subset of di original calldata `(Y)`:

`(X)` is calldata without the input parameter `0000000000000000000000000000000000000000000000000000000000000002` (we no gat keep this one)
and without the constructor code `6080604052348015600f57600080fd5b506040516093380380609383398181016040526020811015602f57600080fd5b81019080805190602001909291905050508060008190555050603e8060556000396000f3fe`Wey suppose run only 1 time.

So `CODECOPY` dey extracts the bytecode from di calldata and copies go de memory.

Make we go the next step.
