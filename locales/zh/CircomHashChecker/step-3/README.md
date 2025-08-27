## 探索 `calculate_hash.circom`

导航到 `circuits` 目录并打开 `calculate_hash.circom` 文件。 该文件包含哈希检查器电路的Circom代码。

### 代码解析

#### 预处理指令和包含文件：

- `pragma circom 2.0.0;` 指定了 Circom 版本。
- `include "circomlib/circuits/poseidon.circom";` 从 [CircomLib](https://github.com/iden/circomlib) 获取并包含 Poseidon 哈希函数。

#### `计算哈希` 模板：

- Defines inputs `value1`, `value2`, `value3`, `value4`.
- Uses the `Poseidon` hash function to compute a hash of these values.\
- Outputs `out`, which is the hash.

#### `HashChecker` Template:

- Inputs are the same values plus a `hash`.
- Instantiates `CalculateHash` as `calculateSecret`.
- Computes `calculatedHash`.
- Uses `assert(hash == calculatedHash);` to ensure the provided hash matches the calculated hash.

#### Main Component:

- `component main {public [hash]} = HashChecker();`
- Specifies that `hash` is a `public` input, while the values are `private`.

### Purpose

The circuit allows someone to prove they know `value1`, `value2`, `value3`, and `value4` that hash to a specific `hash` without revealing the values themselves.