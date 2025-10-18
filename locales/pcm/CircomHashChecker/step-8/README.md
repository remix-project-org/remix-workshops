## To Understand `groth16_trusted_setup.ts`

Navigate go `scripts/groth16/groth16_trusted_setup.ts`. Dis script go perform d trusted setup necessary for generating proofs.

### D code Breakdown

#### Circuit Compilation:

- E dey use`remix.call('circuit-compiler', 'generateR1cs', ...)` take generate `R1CS` (Rank-1 Constraint System) from d circuit.

#### Trusted Setup Steps:

- snarkjs.zKey.newZKey`: go initialize d proving key (`zkey_0\`).
- `snarkjs.zKey.contribute`: dey Add contribution to d proving key (`zkey_1`).
- `snarkjs.zKey.beacon`: dey Finalize d proving key (`zkey_final`).

#### Verification:

- `snarkjs.zKey.verifyFromR1cs`: dey verify d proving key against d `R1CS` and initial parameters.

#### Exporting Keys:

- E dey export the verification key to `scripts/groth16/zk/keys/verification_key.json`.
- E go export d final proving key (`scripts/groth16/zk/keys/zkey_final.txt`).

### Purpose

- E d perform d trusted setup wey `Groth16` require for d proving system.
- E dey generate d necessary keys for proof generation nd verification.

### Execute d Script

- Click d play button wey dey d editor, or right-click d file con select "Run".
- Wait mk d script complete nd `"setup done."` logged in d terminal.