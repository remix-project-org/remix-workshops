## Understanding `groth16_trusted_setup.ts`

Accédez à `scripts/groth16/groth16_trusted_setup.ts`. This script performs the trusted setup necessary for generating proofs.

### Code Breakdown

#### Circuit Compilation:

- Uses `remix.call('circuit-compiler', 'generateR1cs', ...)` to generate `R1CS` (Rank-1 Constraint System) from the circuit.

#### Trusted Setup Steps:

- `snarkjs.zKey.newZKey`: Initializes the proving key (`zkey_0`).
- `snarkjs.zKey.contribute`: Adds contributions to the proving key (`zkey_1`).
- `snarkjs.zKey.beacon`: Finalizes the proving key (`zkey_final`).

#### Vérification :

- `snarkjs.zKey.verifyFromR1cs` : Vérifie la clé de preuve par rapport aux paramètres `R1CS` et initiaux.

#### Exporting Keys:

- Exports the verification key to `scripts/groth16/zk/keys/verification_key.json`.
- Exports the final proving key (`scripts/groth16/zk/keys/zkey_final.txt`).

### Purpose

- Performs the trusted setup required for the `Groth16` proving system.
- Generates the necessary keys for proof generation and verification.

### Execute the Script

- Click the play button in the editor, or right-click the file and select "Run".
- Attendez que le script se termine et `"setup done."` se connecte au terminal.