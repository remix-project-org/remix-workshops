# U go find de offset ;)

And now for a slightly different example:

- Compile notSimpleStore.sol
- Deploy di contract `notSoSimpleStore`
- We go make sure say we get succesful deployment -if dat wan no dey okay u fit still check **de correct input type** foor de constructor.
- U go go de Debugger by clicking de **debug** button for de (successful) creation transaction.
- U go find de value of de parameter of CODECOPY which go represent de offset wey dey calldata where u go copy from.

U go remember: \*codecopy(t, f, s) - copy **s** bytes from code wey dey position **f** to memory for position **t**

If you look in the **Stack**, you go see say the 2nd element na:
0x0000000000000000000000000000000000000000000000000000000000000083

And na e be dis **f** of di input params for di codecopy.

### Shey u been pick up one thin or 2 about how di opcodes do work!