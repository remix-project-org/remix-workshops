When the trusted setup don complete, you fit con compute the witness for your circuit based on inputs wey dey specific.

## Wetin be witness?

- **witness** na set of values wey dey satisfy all the constraints of your circuit. E include all the intermediate numbers and results wey dey satisfy the circuit rules. De witness go dey used for proof wey dey-zero knowledge to te demonsrater dat u go know solution wey good to de problems without de solutoin no go show himself. Dis go allow others to te verify dat u go do everything correctly while keep ur specific nombers and calculations private.
- Im dey essential to dey generate proof.

## U go input values

1. For de **Compute Witness** section u fit see input fields dynamiclly generated based on ur circuits inputs.
2. U go enter values for a and b. For eksampol:
    - a=3
    - b=4

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-6/images/compute_witness.png" alt="compute-witness" width=280 height=240>

## De Computing de witness

1. After u don enter de inputs u go press de**Computa Witness** button.
2. Go compute de witness based oon de inputes wey u don put.
3. If u dey successful u go see \`multiplier.wtn created in de bin directory for de person wey dey exploy file.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-6/images/witness_computed.png" alt="witness-computed" width=340 height=350>

**Note:** If errors dey we go ensure say ur inputs dey valid to dey satisfied de circuit constrait.

In de step we go genera proof wey we dey use de computed witness.
