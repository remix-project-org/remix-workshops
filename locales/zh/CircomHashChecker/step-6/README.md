## 计算见证

1. **访问计算见证部分**：
    - 在可信设置之后，**计算见证**部分可用。

2. **输入值**：
    - You'll see input fields for `value1`, `value2`, `value3`, `value4`, and `hash`.
    - 为每个输入输入值。 例如：
       - `value一`: `一千二百三十四`
       - `value`: `2`
       - `value3`: `三`
       - `value4`: `四`

3. **计算哈希**：

    - 使用与波塞冬哈希函数兼容的外部工具或库计算四个值的波塞冬哈希。
    - 对于上面的值，这里是计算出的波塞冬哈希 \`\`。
    - 在 `hash` 输入字段中输入计算出的 `hash` 值。

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/compute_witness.png" alt="compute-witness" width=250 height=400>

4. \*\*计算见证人：

    - 点击 **计算见证** 按钮。
    - 等待过程完成。 如果证人成功计算，将会出现一个成功徽章。
    - 如果成功，你将在文件资源管理器的 `.bin` 目录中看到 `calculate_hash.wtn` 文件被创建。

         <img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-6/images/witness_computed.png" alt="witness-computed" width=300 height=100>