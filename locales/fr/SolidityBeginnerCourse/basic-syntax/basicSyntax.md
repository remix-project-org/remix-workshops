In this section, we will create our first _smart contract_. Ce contrat se compose uniquement d'une chaîne qui contient la valeur "Hello World !".

In the first line, we should specify the license that we want to use. Vous pouvez trouver une liste complète des licences ici : <0>https://spdx.org/licenses/</0>.

Using the `pragma` keyword (line 3), we specify the Solidity version we want the compiler to use. In this case, it should be greater than or equal to `0.8.3` but less than 0.9.0.

Nous définissons un contrat avec le mot-clé `contrat` et lui donnons un nom, dans ce cas, `HelloWorld` (ligne 5).

Dans notre contrat, nous définissons une _variable d'état_ `greet` qui contient la chaîne `"Hello World !" ` (ligne 6).

Solidity est un langage _statiquement typé_, ce qui signifie que vous devez spécifier le type de la variable lorsque vous la déclarez. Dans ce cas, `greet` est une `chaîne`.

Nous définissons également la _visibilité_ de la variable, qui spécifie d'où vous pouvez y accéder. In this case, it's a `public` variable that you can access from inside and outside the contract.

Don't worry if you didn't understand some concepts like _visibility_, _data types_, or _state variables_. Nous les examinerons dans les sections suivantes.

Pour vous aider à comprendre le code, nous créerons un lien dans toutes les sections suivantes vers des tutoriels vidéo du <a href="https://www.youtube.com/watch?v=g_t0Td4Kr6M" target="_blank">créateur</a> des contrats Solidity by Example.

<0>Regardez un tutoriel vidéo sur la syntaxe de base</0>.

## ⭐️ Affectation

1. Supprimez le contrat HelloWorld et son contenu.
2. Créez un nouveau contrat nommé "MyContract".
3. The contract should have a public state variable called "name" of the type string.
4. Assign the value "Alice" to your new variable.
