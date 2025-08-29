The goal here is to store the code in the blockchain. The EVM needs to tell the client (geth, parity) which what part of the **Call Data** to store.   In this step, we are saving the contract MINUS its constructor (because that gets inplmented only 1 time) and MINUS the input parameter does not need to be stored.

`CODECOPY` is the first step: it copies the bytecode to memory, then the ethereum client will be able to consume it.  MUNCH!

Mais attendez... Avant que le client puisse **MUNCH** bytecode, il a besoin d'une instruction - un opcode pour le dire à MUNCH. `RETURN` is this opcode!

As stated in the general spec, at the end of the contract creation, the client (geth, parity) takes the targeted value by the opcode `RETURN` and **persists** it by making it part of the deployed bytecode.

Once you are in the `CODECOPY`, look at the top 3 items in the **Stack**:

`0: 0x0000000000000000000000000000000000000000000000000000000000000000`
`1: 0x0000000000000000000000000000000000000000000000000000000000000055`
`2: 0x000000000000000000000000000000000000000000000000000000000000003e`

_Dans votre pile - `1` et `2` peuvent être légèrement différents.  The difference may be due to a different compiler version._

**These are the parameters for `CODECOPY`.**

Remember: _codecopy(t, f, s)_ - copy **s** bytes from code at position **f** to memory at position **t**

`0` is the offset where the copied code should be placed in the **memory**. In this example, ( all zeros) the code is copied to the beginning of the memory. (**T**)
`1` est le décalage dans **calldata** d'où copier (**f**)
`2` nombre d'octets à copier - (**s**)

After `CODECOPY` is executed, (click the _step into_ button) the copied code should be:
`0x6080604052600080fdfea265627a7a7231582029bb0975555a15a155e2cf28e025c8d492f0613bfb5cbf96399f6dbd4ea6fc9164736f6c63430005110032` in memory.  **I'll refer to this value as (X)**.

Let's look at the debugger's **Memory** panel.
Le numéro 0x que j'ai donné ci-dessus n'est pas ce que vous verrez dans le panneau **Mémoire** - ce que vous verrez est ceci :
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

The `0x0`, `0x10`, etc is the position. The next number is the bytecode for that position.  This is followed by question marks and seemingly random letters & numbers.  This is **Remix**'s attempt to convert this into a string.

Donc, si nous collons les quatre premières sections de bytecode ensemble, nous obtiendrons :**0x6080604052600080fdfea265627a7a7231582029bb097555a15a155e2cf28e0a6fc9164736f6c63430005110032** La dernière section - `0x90` a 2 qui est ce que j'ai entré pour le paramètre des constructeurs.

Les données d'entrée du panneau **Données d'appel** sont :
`0x6080604052348015600f57600080fd5b506040516093380309383398181016040526020811015602f5760008080fd5b81019080801906020190929190505050508060008190555050603e8060556000396000f3fe60806040526000080fdfea265627a7a7231582029bb097555a15a155e155e2cf28e025c8d492f0613bfbfb5cb96399f6dbd4ea6fc9164736c634300051100320000000000000000000000000000000000000000000000000000000002`
\*\*Je vais faire référence à cette valeur comme (Y). \*\*

This shows us that `(X)` is a subset of the original calldata `(Y)`:

`(X)` est des données d'appel sans le paramètre d'entrée `00000000000000000000000000000000000000000000000000000000000000000000000002` (nous n'avons pas besoin de le stocker)
Et sans le code constructeur `6080604052348015600f57600080fd5b506040516093380380609383398181016040526020811015602f57600080fd5b810190808051906020019092919050508060008190555050603e8060556000396000f3fe` qui ne devrait être exécuté qu'une seule fois.

So `CODECOPY` extracts the bytecode from the calldata and copies it to the memory.

Let's move to the next step.
