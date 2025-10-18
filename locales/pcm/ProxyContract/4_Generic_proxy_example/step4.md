# Di Basic Generic Proxy Example

For di associated solidity file **step4.sol**, there are 2 contracts - **ProxyContract** and **LogicContract**.

To fit use dis system we first deploy di logicContract.

When we go deploydi proxyContract, we pass di logic contract address as an argument of di proxycontract's constructor.

Di proxycontract dey deploy for once.

Di code of logiccontract fit be call di line 20. Dem fit forward di delegate call while keeping di contract of logic contract.

In case we need change di logic we fit deploy new logiccontract and set di address of am with setLogicContractAddress setter function.

note say di logiccontract we get di storage. Once u need use di storage di implement go become a bit more complicated becuz those contract share di context