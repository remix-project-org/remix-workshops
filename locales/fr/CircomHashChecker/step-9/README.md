## Understanding `groth16_zkproof.ts`

Navigate to `scripts/groth16/groth16_zkproof.ts`. This script generates the zero-knowledge proof and prepares it for verification.

### Code Overview

#### Loading Files:

- Lit les fichiers R1CS et WASM générés par le circuit.
- Loads the final proving key (`zkey_final`) and verification key (`vKey`).

#### Defining Inputs:

- Sets the private values (`value1`, `value2`, `value3`, `value4`).
- Computes the `hash` using Poseidon from [CircomLib](https://github.com/iden3/circomlib).

#### Witness Calculation and Proof Generation:

- Calculates the witness (`wtns`).
- Checks the witness against the `R1CS`.
- Génère la preuve en utilisant `Groth16`.
- Verifies the proof.

#### Exporting Verifier Contract and Inputs:

- Generates a Solidity verifier contract.
- Exports the proof inputs to `input.json`.

### Purpose

- Génère une preuve à connaissance nulle que le prover sait que les valeurs de hachage à un hachage spécifique.
- Prepares the verifier contract and inputs for on-chain verification.

### Exécuter le script

- Cliquez sur le bouton de lecture dans l'éditeur, ou cliquez avec le bouton droit de la souris sur le fichier et sélectionnez "Exécuter".
- Attendez que le script soit terminé et que `"zk proof validity"` soit enregistré dans le terminal.