Une norme de jeton nous indique de quelle fonctionnalité le contrat a besoin pour s'y conformer. How this functionality is implemented is up to the developers. Dans ce contrat, nous utiliserons une implémentation de contrat de jeton ERC20 d'OpenZeppelin (ligne 4). In this case, we import version 4.4.0 of the OpenZeppelin contracts.

Jetez un coup d'œil à leur <0>contrat ERC20</0> bien documenté pour mieux comprendre à quoi pourrait ressembler une mise en œuvre. Apart from the functionality specified in the ERC20 standard, this contract provides additional functionality.

Nous allons créer notre propre contrat appelé MyToken (ligne 6), qui hérite de la fonctionnalité de l'implémentation du contrat de jeton OpenZepplin ERC20 que nous avons importé (ligne 4).

Ce contrat implémente les fonctions facultatives `name()` et `symbol()` de la norme ERC20 Token et dispose d'un constructeur où leurs valeurs peuvent être définies pendant le déploiement du contrat (ligne 7).
In this case, we are going to use the default values. We will call our token the same as the contract `"MyToken"` and make `"MTK"` its symbol.

Next, we make use of the inherited `_mint` function (line 8) that allows us to create tokens upon deployment of the contract. Inside the parameters, we specify the address of the account that receives the tokens and the amount of tokens that are created.
In this case, the account that deploys the contract will receive the tokens and we set the amount to 1000000 to the power of `decimals()`. The optional function `decimals()` of the ERC20 token standard is implemented and set to the default value of 18. Cela créera 1000000 jetons qui auront 18 décimales.

## ⭐️ Assignment

1. Rename your contract to `EduCoin`.
2. Rename your token to `EduCoin`.
3. Change the symbol of your token to `EDC`.
4. Change the amount of tokens that will be minted from 1000000 to 1000.