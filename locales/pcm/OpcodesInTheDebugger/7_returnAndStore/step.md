# Opcode don come back

For the end of the chapter wey we jus finish, we dom carry another leg after **CODECOPY** make we fit see wetin sup for the memory.

Now wey CODECOPY don launch, we don dey opcode `PUSH1 00`.

`PUSH1 00` dey prepare the stack for `RETURN` opcode.
`RETURN` na the fina part for this process.  Na where dem dey return code to customer.

We push `00` go stack becos na the position wey bytecode contract for memory no balance.

Now we fit call `RETURN` opcode wey dey important.

Return the **stack inspector** dey show: `0: 0x0000000000000000000000000000000000000000000000000000000000000000`
`1: 0x000000000000000000000000000000000000000000000000000000000000003e`

Wetin e mean na say e dey go back client di bytecode starting `0x00` wit length `0x3e`.
