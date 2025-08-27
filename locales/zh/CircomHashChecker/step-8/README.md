## 理解 `groth十六_trusted_setup.ts`

导航到 `scripts/groth十六/groth十六_trusted_setup.ts`。 该脚本执行生成证明所需的可信设置。

### 代码解析

#### 电路汇编：

- 使用 `remix.call('circuit-compiler', 'generateR一cs', ...)` 从电路生成 `R一CS`（一级约束系统）。

#### 可信设置步骤：

- `snarkjs.zKey.newZKey`: 初始化证明密钥 (`zkey_0`)。
- `snarkjs.zKey.contribute`: 向证明密钥（`zkey_1`）添加贡献。
- `snarkjs.zKey.beacon`：最终确定证明密钥（`zkey_final`）。

#### Verification:

- `snarkjs.zKey.verifyFromR一cs`: 验证证明密钥与 `R一CS` 和初始参数。

#### 导出密钥：

- 将验证密钥导出到 `scripts/groth十六/zk/keys/verification_key.json`。
- 导出最终证明密钥（`scripts/groth十六/zk/keys/zkey_final.txt`）。

### 目的

- 执行 `Groth十六` 证明系统所需的可信设置。
- 生成生成证明和验证所需的密钥。

### 执行脚本

- 在编辑器中点击播放按钮，或者右键点击文件并选择 "运行"。
- 等待脚本完成，并在终端中记录"设置完成。"