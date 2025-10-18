Dis section go dey into di types of fuktion wey no dey modify di state of di blockchain "view" and "pure" fuktions.

### View fuktions

"View fuktions" promise to not modify di state.

"Di following statements dey considered modifing di state:

1. We dey write state variables.
2. Emitting events.
3. Creating other kontracts.
4. Using selfdestruct.
5. Sending Ether via calls.
6. Wey dey call any fuktion not marked view or pure.
7. Dey use low-level calls.
8. Using inline assembli wey contain certain opcodes."

From di <a href="https://docs.soliditylang.org/en/latest/contracts.html#view-functions" target="_blank">Solidity dokumentation</a>.

U fit declare one view fuktions wey u dey use di keyword 'view'. In dis kontract, 'addTox' (line 8) na one view fuktion,. Dis fuktion dey carry di parameter 'y' and returns di sum of di parameter and di state variable 'x'. E dey read 'x' but e no dey modify am.

### Fuktion wey dey clean

_Fuktion wey dey clean_promise to neither modify nor to read di state.

'In addition to di list for state wey modify statement explained above, di following dey consider wey u fit read from di state:

1. We dey read am from state variables.
2. Give permission 'addresa(Dis). balance' or'<address>. balance'.
3. Give permission of di members of block, tx, msg (wit di expecting of 'msg.sig' and 'msg.data').
4. Dey call any fuktion wey no dey pure.
5. Dey use inline assembli wey kontain certain opcodes."

From di <a href="https://docs.soliditylang.org/en/latest/contracts.html#pure-functions" target="_blank">Solidity dokumentation </a>.

You fit declare pure fuktion wey u fit use di keyword 'pure'. For dis kontract, 'add' (line 13) na pure fuktion. Dis fuktion takes di parameters 'i' and 'j', and returns di sum of dem. It neither reads nor modifies di state variable 'x'.

For Solidity development, you go need optimize ya code for saving komputation cost (gas cost). Declaring fuktion view and pure fit save gas cost and make di code more visible and e dey way to maintain. Pure fuktions no get any side effects and e go always dey return di same result if you pass di same arguments.

<a href="https://www.youtube.com/watch?v=vOmXqJ4Qzbc" target="_blank">Watch video tutorial for View and pure fuktions </a>.

## ⭐️ Assignment

Create one fuktion wey we fit call 'addTox2' wey dey take did parameter 'y' and update do state variable 'x' wit di sum of di parameter and di state variable 'x'.