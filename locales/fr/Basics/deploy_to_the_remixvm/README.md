Dans le chapitre précédent, nous avons compilé un contrat - c'est-à-dire que le code Solidity a été transformé en petits morceaux de bytecode de la Machine Virtuelle Ethereum (EVM).

Maintenant, nous allons placer ce code sur une blockchain de test.

1. Cliquez sur l'icône Déployer et Exécuter icône ![déployer & exécuter](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_to_the_remixvm/images/run.png "deploy & run icon").

2. Sélectionnez l'une des VM Remix dans le menu déroulant Environnement.

3. Cliquez sur le bouton Déployer (ou le bouton de transaction dans la vue étendue).

4. Vous avez déployé votre contrat compilé sur la VM Remix - une blockchain simulée qui s'exécute dans la fenêtre de votre navigateur.  La VM Remix est une chaîne de test simple et rapide.  Elle n'est pas très réaliste car vous n'avez pas besoin d'approuver chaque transaction.

5. Vérifiez le terminal pour voir les détails de cette transaction de déploiement.

Vous pouvez également utiliser Remix pour déployer sur d'autres chaînes EVM publiques. Pour ce faire, vous devrez vous connecter à un autre Environnement - comme Fournisseur Injecté.  Le Fournisseur Injecté connecte Remix au portefeuille du navigateur (comme MetaMask ou similaire).  Nous essaierons de déployer sur un réseau public à la fin de ce tutoriel. Mais avant d'y arriver, nous aborderons comment interagir avec les fonctions d'un contrat déployé.
