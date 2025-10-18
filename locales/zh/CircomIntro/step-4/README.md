在准备好你的 `multiplier.circom` 电路后，让我们使用电路编译器插件进行编译。

## 选择编译器版本

下拉菜单选择所需**编译器版本**。 在本教程中，请选择最新的稳定版本。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-4/images/select_compiler_version.png" alt="select-compiler-version" width=250 height=100>

## 配置编译选项

- **自动编译：** 你可以启用此选项，以便在保存更改时自动编译你的电路。
- **隐藏警告：** 启用此选项可以隐藏编译器的警告（如果有的话）。
- **高级配置:**
  - 点击展开。
  - 选择 **Prime Field**。 在大多数情况下，`BN128`已足够。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-4/images/advanced_configuration.png" alt="advanced-configuration" width=300 height=100>

## 编译电路

1. 点击**编译**按钮。
2. 编译器将处理您的电路。
3. 如果成功，您将看到一个编译成功的消息。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-4/images/compilation_success.png" alt="compilation-success" width=200 height=400>

**注意：** 如果出现任何错误，它们将显示在控制台中。 检查您的代码是否有拼写错误或语法错误。

## 理解编译输出

- 成功编译后，**设置和导出**部分会变得可见。
- 您可以继续执行下一步进行可信设置。

在下一步中，我们将使用编译后的电路进行可信设置。
