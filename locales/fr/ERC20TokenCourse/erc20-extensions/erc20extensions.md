La norme ERC20 ne décrit que les fonctionnalités requises et facultatives dont votre contrat a besoin, mais vous pouvez ajouter des fonctionnalités supplémentaires.

Dans cette section, nous avons ajouté la fonctionnalité de gravure et de frappe de jetons, ainsi que la possibilité de mettre en pause le contrat, en utilisant les extensions OpenZeppelin.

Of course, you can write your own ERC20 token contract implementation or extensions and import them into your contract. Mais les contrats OpenZeppelin ont été audités par des experts en sécurité et sont un excellent moyen d'ajouter la fonctionnalité souhaitée.

### Mintable

The mint function allows the creator of the contract to mint (create) additional tokens after the contract has been deployed (line 22). As input parameters, the function needs the address that the tokens will be minted to, and the amount of tokens that should be minted.

Nous n'avons pas besoin d'importer `mint()` à partir d'un autre contrat puisque la fonction mint fait déjà partie de l'implémentation <0>contrat ERC20</0> d'OpenZeppelin. We import `Ownable` (line 7) which is a contract module that provides a basic access control mechanism that allows an owner to have exclusive access to specific functions. In this contract, we add the inherited `onlyOwner` modifier to the `mint` function (line 22) and restrict access to this function to the "owner".

Le contrat héritera de fonctions supplémentaires telles que owner(), transferOwnership() et renounceOwnership() pour gérer l'accès, à partir du <0>Contrat Ownerable</0>.

### Burnable

En important le "ERC20Burnable" (ligne 5) et en héritant de ses fonctions (ligne 9), notre contrat permet aux détenteurs de jetons de détruire leurs jetons ainsi que les jetons de leur allocation.
Pour plus d'informations, jetez un coup d'œil au <0>contrat ERC20Burnable</0>.

### Pausable

Avec le module de contrat "Pauseable" (lignes 6 et 9), le propriétaire est en mesure de mettre en pause (ligne 14) et d'interrompre (ligne 18) le contrat. In the pause state, tokens can't be transferred, which can be helpful in emergency scenarios.
Pour plus d'informations, jetez un coup d'œil au <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/security/Pausable.sol" target="_blank">contrat en pause</a>.

Jetez un coup d'œil à l'OpenZeppelins <0>Contract Wizard</0>, qui vous permet d'ajouter facilement des fonctionnalités supplémentaires.

Si vous avez terminé ce cours avec succès, essayez le cours Learneth NFT comme prochaine étape de votre parcours.

## ⭐️ Affectation

1. Essayez de frapper des jetons sur un compte après le déploiement. Call `totalSupply()` and `balanceOf()` to confirm the correct execution.
2. Brûlez des jetons, puis appelez `totalSupply()` et `balanceOf()` pour confirmer l'exécution correcte.
3. Testez la fonction de pause en suspendant le contrat en utilisant le compte du propriétaire et en essayant d'efectuer un transfert avec un deuxième compte. The transaction should not be able to be executed and will throw the exception: "Pausable: paused".
