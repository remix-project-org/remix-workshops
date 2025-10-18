Une bibliothèque ressemble à un contrat mais utilise le mot-clé library.

Une bibliothèque est généralement une collection de fonctions utiles situées sur la blockchain que n'importe quel contrat peut utiliser.  Comme la bibliothèque est déjà déployée, cela économise les coûts de déploiement des nombreux contrats qui l'utilisent.

Dans le contrat suivant :

- Créez une bibliothèque nommée LibraryForTest.

Il est possible de placer une bibliothèque dans le même fichier qu'un autre contrat.  Placez donc la bibliothèque sous le contrat.

Cette bibliothèque doit avoir une méthode appelée getFromLib qui retourne 3.

- Mettez à jour la méthode get dans le contrat test pour utiliser la bibliothèque LibraryForTest.   La fonction get doit retourner la valeur qu'elle reçoit de getFromLib.

---------

Vous pouvez trouver plus d'informations sur les bibliothèques dans <a href="https://solidity.readthedocs.io/en/latest/contracts.html?highlight=library#libraries" target="_blank">cette section de la documentation Solidity</a>.
