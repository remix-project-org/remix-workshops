## 编译电路

### 选择编译器版本选择编译器版本

1. 前往侧边栏中的 **Circuit Compiler** 插件。
2. 从下拉菜单中选择所需的 **编译器版本**。 在本教程中，请选择最新的稳定版本。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-4/images/select_compiler_version.png" alt="select-compiler-version" width=250 height=100>

### 配置编译选项

- **自动编译:** 您可以启用此选项，在您保存更改时自动编译电路。
- \*\*隐藏警告：\*\*启用此选项可以抑制编译器的警告 如果有的话。
- **高级配置：**
  - 点击展开。
  - 选择**素数域**。 在大多数情况下，`BN` 是足够的。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-4/images/advanced_configuration.png" alt="advanced-configuration" width=300 height=100>

### 编译电路

1. 点击**编译**按钮。
2. 等待编译完成。 如果编译成功，将出现一枚成功徽章。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomHashChecker/step-4/images/compilation_success.png" alt="compilation-success" width=300 height=675>

### 理解编译输出

- 成功编译后，**设置和导出**部分变为可见。
- 您可以继续下一步进行可信设置。

在下一步中，我们将使用编译后的电路进行可信设置。