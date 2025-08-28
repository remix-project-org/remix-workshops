# U go find de offset ;)

And now for a slightly different example:

- Compile notSimpleStore.sol
- Deploy di contract `notSoSimpleStore`
- We go make sure say we get succesful deployment -if dat wan no dey okay u fit still check **de correct input type** foor de constructor.
- U go go de Debugger by clicking de **debug** button for de (successful) creation transaction.
- U go find de value of de parameter of CODECOPY which go represent de offset wey dey calldata where u go copy from.

U go remember: \*codecopy(t, f, s) - copy **s** bytes from code wey dey position **f** to memory for position **t**

If you look in the **Stack**, you should see that the 2nd element is:
0x0000000000000000000000000000000000000000000000000000000000000083

And this is the **f** of the input params of codecopy.

### Hope you picked up a thing or 2 about how opcodes work!