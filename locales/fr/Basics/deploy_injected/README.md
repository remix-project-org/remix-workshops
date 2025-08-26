1. Si vous n'avez pas de portefeuille Ethereum dans votre navigateur (ex : **Metamask**), téléchargez et installez en un maintenant.

2. Cliquez sur l'icône MetaMask dans votre navigateur. Connectez-vous et choisissez le réseau de test Ephemery. Vous devrez probablement changer les réglages de votre portefeuille pour voir les **réseaux de test**.  Vous pouvez aussi vous rendre dans le module de transaction Remix "Deploy & Run" et dans la section ENVIRONMENT, choisir Ephemery.

3. Obtenir des ETH dans un réseau de test public est souvent gênant.  Ephemery est un réseau de test public qui est remis à zéro mensuellement. Obtenir des ETH de test ne devrait pas poser de problème.  Voici un lien vers des <a href="https://github.com/ephemery-testnet/ephemery-resources?tab=readme-ov-file#faucets" target="_blank">faucets Ephemery</a>.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/testnet.png)

Sepolia est un autre réseau de test populaire qui n'est pas remis à zéro : les déploiements y persistent, mais les faucets Sepolia sont plus difficile à utilier.

Dans le portefeuille de votre navigateur, assurez-vous de ne PAS avoir sélectionné "mainnet" ou tout autre réseau qui vous coûterai de vrais ETH. In the Deploy & Run module, below the Environment select box, you'll see a badge with the network's ID and for popular chains, its name.  In the case below its Sepolia.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/sepolia.png)

5. Make sure you see the 2_Owner.sol as a choice in the **CONTRACT** select box, then click the **Deploy** button.

If the **CONTRACT** select box is empty, you'll need to compile 2_Owner again by making 2_Owner.sol the active file in the **editor** and then go to the **Solidity Compiler** to compile it.

6. After you hit the `Deploy` button, you'll see the browser wallet popup asking you to pay for the transactions.  If you have the appropriate kind of ETH for this chain, approve this transaction.  Check the printout in the terminal.  Once the block is validated, the **deployed instance** will appear at the bottom of Deploy & Run

And with that you have finished this tutorial.  You now have experience with opening, compiling, deploying and interacting with Smart Contracts in Remix IDE.
