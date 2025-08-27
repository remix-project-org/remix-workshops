After compiling your circuit, you gats perform trusted setup wey go generate proving and verification keys.

## How to take understand trusted setup

- Trusted Setup: na process wey dey required for zk-SNARKs to take generate the parameters wey you need for proof generation and verification.
- You fit choose between different protocols like Groth16 and plonk.

## How to take perform the trusted setup

1. For the setup and exports section, click the proving scheme:
    - You go con choose between groth16 or plonk. We go use groth16 do this tutorial.

2. Choose the correct power of tau file wey dey the dropdown. This file dey important for trusted setup.
    - If you no too sure, click the default option.

3. Click the setup button if you wan restart the trusted setup process.

4. You fit enable export verification key make we dey get the verification parameters.

5. You fit enable export verification contract if you wan verify onchain proofs.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-5/images/trusted_setup.png" alt="trusted-setup" width=330 height=350>

No forget: the trusted setup fit take time, e go depend on how your circuit complex reach.

For the next step, we go enter the witness for our circuit.
