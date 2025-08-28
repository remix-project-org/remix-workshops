在计算出见证值后，最后一步是生成一个可以被他人验证的证明。

## 生成证明

1. 在 **生成证明** 部分，您可以选择 **导出验证器的调用数据**。
    - 如果您计划在链上验证证明，请启用 **Export Verifier Calldata** 复选框。
2. 点击 **Generate Proof**按钮。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/generate_proof.png" alt="generate-proof" width=280 height=120>

## 了解输出

- 证明生成后，插件将显示验证数据。
- 如果你启用了 **Export Verifier Calldata**，你还会获得链上验证所需的调用数据。

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/proof_generated.png" alt="proof-generated" width=310 height=350>

## 下一步

- **验证:** 您可以使用之前导出的验证密钥或合约来验证证明。
- **链上验证：** 如果您熟悉智能合约，可以部署验证合约并使用 Calldata 来执行链上验证。

\*\*恭喜！\*\*您已成功编写了 Circom 电路、对其进行了编译、执行了可信设置、计算了见证值，并使用 Remix-IDE 生成了证明。

## 附加资源

- [Circom 文档](https://docs.circom.io/)
- [Remix-IDE 文档](https://remix-ide.readthedocs.io/)
- [零知识证明诠释](https://zkproof.org/)

请尽管尝试更复杂的电路，并进一步探索 Circom 和 Remix-IDE 的功能。
