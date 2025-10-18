## 探索 `calculate_hash.circom`

导航到 `circuits` 目录并打开 `calculate_hash.circom` 文件。 该文件包含哈希检查器电路的Circom代码。

### 代码解析

#### 预处理指令和包含文件：

- `pragma circom 2.0.0;` 指定了 Circom 版本。
- `include "circomlib/circuits/poseidon.circom";` 从 [CircomLib](https://github.com/iden/circomlib) 获取并包含 Poseidon 哈希函数。

#### `计算哈希` 模板：

- 定义输入 `value`、`value`、`value`、`value`。
- 使用 `Poseidon` 哈希函数来计算这些值的哈希
- 输出 `out`，这是哈希值。

#### `HashChecker` 模板：

- 输入是相同的值加上一个`hash`。
- 将 `CalculateHash` 实例化为 `calculateSecret`。
- 计算 `calculatedHash`。
- 使用 `assert(hash == calculatedHash);` 确保提供的哈希与计算得到的哈希匹配。

#### 主要组成部分：

- `组件主 {公共 [哈希]} = 哈希检查器();`
- 指定 `hash` 是一个 `public` 输入，而这些值则是 `private`。

### 目的

该电路允许某人证明他们知道`value`、`value`、`value`和`value`，这些值的哈希值为特定的`hash`，而不透露这些值本身。