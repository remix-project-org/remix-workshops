完成可信设置后，您现在可以根据特定的输入计算电路的见证值。

## 什么是见证值？

- **见证值** 是一组满足电路所有约束的值。 它包含了所有满足电路规则的中间数值和结果。 零知识证明中使用见证值来表明您知道问题的有效解决方案，而无需实际展示解决方案本身。 这样，其他人就可以验证您是否正确完成了所有操作，同时保证您的具体数字和计算的私密性。
- 这对于生成证明至关重要。

## 输入值

1. 在 **计算见证值** 部分，您将看到根据电路输入动态生成的输入字段。
2. 输入 `a` 和 `b` 的值。 例如：
    - `a = 3`
    - `b = 4`

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-6/images/compute_witness.png" alt="compute-witness" width=280 height=240>

## 计算见证值

1. 输入输入后点击**计算见证值** 按钮。
2. 插件将根据您的输入计算见证值。
3. 如果成功，您将在文件资源管理器的 `.bin` 目录中看到创建的 `multiplier.wtn` 文件。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-6/images/witness_computed.png" alt="witness-computed" width=340 height=350>

**注意：** 如果出现任何错误，请确保您的输入有效并满足电路的约束条件。

在下一步中，我们将使用计算出的见证值生成证明。
