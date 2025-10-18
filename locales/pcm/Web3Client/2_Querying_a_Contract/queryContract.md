Now we sabi how to query simple data make we try complex one.

Dis contract deployed go di mainnet for dis address<a href="https://etherscan.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7#code" target="_blank">https://etherscan.io/address/0xdac17f958d2ee523a2206206994597c13d831ec7#code</a>

We dey go query di contract to fit find di name of im token.

Di **name** variable is a state variable of the contract.

To fit access dis **mainnet**contract, we go need do setup.

1. Change am go mainnet for metamask.
2. U fit probably need refresh remix.
3. As dey result of refresh u fit need reload dis tutorial too.
4. Go deploy run am and switch to **injectedweb3**.

use web3
for di script querycontract.js, we fit need to instantiate new instance of web3.eth.contract object.  We must grab di contract's ABI and im address.  Di source code annd im ABI dey availablefor etherscan becuz di contract developer intentionally make am.

For etherscan we fit name am **tether token**.  To move downn go tether token contract in di source code place of etherscan we fit state variables for di contract di first of which e named am **name**.

Dem dey few syntactic hoops to fit jump pass to return di value of di state variable.

- To fit generate getter function of di public state variable, u need both treat di variable as a function ( by adding parentheses) and to fit tack di call.
