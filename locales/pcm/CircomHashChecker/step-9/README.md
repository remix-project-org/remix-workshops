## Understanding `groth16_zkproof.ts`

Navigate go `scripts/groth16/groth16_zkproof.ts`. This script dey generate zero-knowledege proof con still prepare am for verification.

### Code Overview

#### Loading Files:

- E go read d R1CS and WASM files wey generate from d circuit.
- E dey load the final proving key (`zkey_final`) and verification key (`vKey`).

#### To define Inputs:

- E dey set d private values (`value1`, `value2`, `value3`, `value4`).
- Computes the `hash` using Poseidon from [CircomLib](https://github.com/iden3/circomlib).

#### Witness Calculation and Proof Generation:

- E dey calculate d witness (`wtns`).
- E go check d witness against d `R1CS`.
- E go generate d proof using `Groth16`.
- E go verify d proof.

#### To export Verifier Contract and Inputs:

- E dey generate Solidity verifier contract.
- E dey export d proof inputs go `input.json`.

### Purpose

- E dey Generate zero-knowledge proof say d prover know d value of hashing to a specific hash.
- E dey prepare d verifier contract nd inputs for on-chain verification.

### Finish d Script

- Click d play button wey dey d editor, abi make yu right-click d file con select "Run".
- Wait make d script complete and `"zk proof validity"` logged in d terminal.