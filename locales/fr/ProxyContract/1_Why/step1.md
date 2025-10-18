# Proxy Contract AKA the Dispatcher

## Why?

C'est un excellent modèle qui est principalement utilisé dans **le développement de la bibliothèque**.

Il aide de la manière suivante :

- **Économisez le coût de l'essence au moment du déploiement**
  Le but d'un coût de gaz élevé est de décourager les opérations qui coûtent cher leur exécution et d'encourager un code optimisé.

- Proxy contracts are useful when a lot of instances of the same contract need to be deployed because they reduce the duplications in the deployment.

- \*\*Évitez la répétition du code dans la blockchain. \*\*Les calculs lourds sont coûteux parce que chaque nœud devra les effectuer, ce qui ralentit bien sûr le réseau.

- **Develop upgradable(versioned) contracts**
  When the contract is deployed, it’s immutable. En redessinant le code en différents contrats, il est possible d'autoriser les mises à niveau logiques tout en conservant le même stockage.

## Example of gas cost

Storing contract code at creation time can cost up to:

- 200 \* max_byte_code_length gas
- 200 \* 24576 = 49152004915200 \* 10 gwei = 49152000 gwei = 0.049152 ether = 9 EUR

see https://github.com/ethereum/EIPs/blob/master/EIPS/eip-170.md Pour plus d'informations sur max_byte_code_length.
