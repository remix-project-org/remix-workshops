1. Si vous n'avez pas de portefeuille Ethereum dans votre navigateur (ex : **Metamask**), téléchargez et installez en un maintenant.

2. Cliquez sur l'icône MetaMask dans votre navigateur. Connectez-vous et choisissez le réseau de test Ephemery. Vous devrez probablement changer les réglages de votre portefeuille pour voir les **réseaux de test**.  Vous pouvez aussi vous rendre dans le module de transaction Remix "Deploy & Run" et dans la section ENVIRONMENT, choisir Ephemery.

3. Obtenir des ETH dans un réseau de test public est souvent gênant.  Ephemery est un réseau de test public qui est remis à zéro mensuellement. Obtenir des ETH de test ne devrait pas poser de problème.  Voici un lien vers des <a href="https://github.com/ephemery-testnet/ephemery-resources?tab=readme-ov-file#faucets" target="_blank">faucets Ephemery</a>.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/testnet.png)

Sepolia est un autre réseau de test populaire qui n'est pas remis à zéro : les déploiements y persistent, mais les faucets Sepolia sont plus difficile à utilier.

Dans le portefeuille de votre navigateur, assurez-vous de ne PAS avoir sélectionné "mainnet" ou tout autre réseau qui vous coûterai de vrais ETH. Si vous n'avez pas de portefeuille de navigateur comme MetaMask, téléchargez et installez-en un maintenant.  In the case below its Sepolia.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/sepolia.png)

5. Assurez-vous de voir 2_Owner.sol comme option dans la boîte de sélection CONTRACT, puis cliquez sur le bouton Déployer.

Si la boîte de sélection CONTRACT est vide, vous devrez compiler à nouveau 2_Owner en faisant de 2_Owner.sol le fichier actif dans l'éditeur, puis aller dans le Compilateur Solidity pour le compiler.

6. Après avoir cliqué sur le bouton Déployer, vous verrez une fenêtre contextuelle du portefeuille du navigateur vous demandant de payer les transactions.  Si vous avez le type approprié d'ETH pour cette chaîne, approuvez cette transaction.  Vérifiez l'affichage dans le terminal.  Une fois le bloc validé, l'instance déployée apparaîtra en bas de Déployer & Exécuter

Et avec cela, vous avez terminé ce tutoriel.  Vous avez maintenant de l'expérience avec l'ouverture, la compilation, le déploiement et l'interaction avec les contrats intelligents dans Remix IDE.
