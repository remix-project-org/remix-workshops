## 理解 `groth十六_zkproof.ts`

导航到 `scripts/groth十六/groth十六_zkproof.ts`。 该脚本生成零知识证明并准备进行验证。

### 代码概述

#### 加载文件：

- Reads the R1CS and WASM files generated from the circuit.
- 加载最终证明密钥（`zkey_final`）和验证密钥（`vKey`）。

#### 定义输入：

- 设置私有值（`value一`，`value二`，`value三`，`value四`）。
- 使用来自 [CircomLib](https://github.com三/iden/circomlib) 的 Poseidon 计算 `hash`。

#### 见算证生：

- 计见证 (wtns)。
- 按"R一CS"验见证人。
- 以"Groth十六"为验。
- 验之。

#### 导出验证者合约和输：

- 创建 Solidity 验证器合约。
- 输入导出至"input.json"。

### 志也

- 创一个零知之验,证者有哈希到特定哈希直之直。
- 将验证者合约输以验链上。

### 行脚本

- 单击编辑器中播放按钮,或右键单击文而择"行"。
- 待脚本成行,书于终端术语"zk 有效性"。