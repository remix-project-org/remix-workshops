## 理解 `groth十六_zkproof.ts`

导航到 `scripts/groth十六/groth十六_zkproof.ts`。 该脚本生成零知识证明并准备进行验证。

### 代码概述

#### 加载文件：

- Reads the R1CS and WASM files generated from the circuit.
- 加载最终证明密钥（`zkey_final`）和验证密钥（`vKey`）。

#### 定义输入：

- 设置私有值（`value一`，`value二`，`value三`，`value四`）。
- Computes the `hash` using Poseidon from [CircomLib](https://github.com/iden3/circomlib).

#### Witness Calculation and Proof Generation:

- Calculates the witness (`wtns`).
- Checks the witness against the `R1CS`.
- Generates the proof using `Groth16`.
- Verifies the proof.

#### Exporting Verifier Contract and Inputs:

- Generates a Solidity verifier contract.
- Exports the proof inputs to `input.json`.

### Purpose

- Generates a zero-knowledge proof that the prover knows values hashing to a specific hash.
- Prepares the verifier contract and inputs for on-chain verification.

### Execute the Script

- Click the play button in the editor, or right-click the file and select "Run".
- Wait for the script to complete and `"zk proof validity"` logged in the terminal.