This section go give short introduction ontop functions nd teach you how to dey use them to read from nd write to a state variable.

As e be for other languages, we dey use functions in Solidity take create modular, reusable code. But as e be, Solidity functions get some particularities.

Solidity functions fit dey split into two types:

1. Functions wey modify di state of d iblockchain, like writing to a state variable. For dis contract de set of function (line 9) go change de state of variable num.
2. Functions wey no dey modify de state of de blockchain. Dis functions dey marked view or pure. For eksampol for dis contract de get functions (line14) don dey marked view wey fit only return num no dey change de state.

To te define a function u go use de functions keyword wey follow by name wey unique.

If de function don take inputs wey be like our set os functions (line 9), u must specify de pererimeter types and names. A common convention na to use underscore wey be like prefix for de parameter name distiguish dem from state wy get variables.

You fit den set de visibility of function and declare dem or pure as we dey do for de get function if dey no modify de state. Our get functions also dey return values so we go have to specify de return types. For dis case na unit since de state variable num dat de function go return as unit.

We go exploi de particularities of solidity functions for more detailes for de following sections.

<a href="https://www.youtube.com/watch?v=Mm6834AAY00" target="_blank">U go watch video tutorial wen u dey send Ether</a>.

## De Assignment

1. U go Create public state variable wey dem dey call b na of de type bool and u go initialize am to trure.
2. U go create public function called get ey go return de value of b.