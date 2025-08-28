让我们编写一个简单的 Circom 电路。

## 创建一个新的电路文件

1. 在左侧边栏的 **文件资源管理器** 中，点击 **创建新文件** 图标。
2. 将文件命名为 `multiplier.circom`，然后按 **Enter** 键。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-3/images/create_new_file.png" alt="create-new-file" width=300 height=200>

## 编写电路

打开 `multiplier.circom` 文件并添加以下代码：

```circom
pragma circom 2.0.0;

template Multiplier() {
    signal input a;
    signal input b;
    signal output c;

    c <== a * b;
}
```

## 拆解：

- 模板 `Multiplier()`：定义了一个名为 Multiplier 的新电路模板。
- `signal input a;` 和 `signal input b;`：声明输入信号 `a` 和 `b`。
- `signal output c;`：声明一个输出信号 `c`。
- `c <== a * b;`：将 `c` 限制为 `a` 和 `b` 的乘积。
- `component main = Multiplier();`：实例化 `Multiplier` 电路为 `main`，这是编译器所需的。

### 注意;

信号是加密电路中的值，这些值严格由电路的方程式和约束决定。
将信号看作是一个必须遵循电路中定义的特定数学规则的值——一旦设置，它就不能随意更改。
在常规编程中，变量是灵活的，可以根据需要更新或重新赋值，而信号则不能随意更改 。
