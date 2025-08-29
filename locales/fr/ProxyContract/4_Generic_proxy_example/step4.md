# Un Exemple De Proxy Générique De Base

Dans le fichier de solidité associé, **step4.sol**, il y a 2 contrats - **ProxyContract** et **LogicContract**.

Pour utiliser ce système, nous déployons d'abord LogicContract.

And then when we go to deploy the ProxyContract, we pass the LogicContract's address as an argument of the ProxyContract's constructor.

The ProxyContract is deployed only once.

The code of LogicContract will be called at the line 20. It will be forwarded with delegate call while keeping the context of LogicContract.

In case we need to change the logic we would deploy a new LogicContract and set the address of it with setLogicContractAddress setter function.

_Remarque : Le LogicContract que nous avons ici n'utilise pas le stockage. Once you need to use the storage the implementation becomes a bit more complicated because those contracts share the context._