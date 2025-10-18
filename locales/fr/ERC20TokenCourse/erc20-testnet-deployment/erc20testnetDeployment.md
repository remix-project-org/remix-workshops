In this section, we will use Metamask (an Ethereum wallet) to deploy our contract to a testnet of the Ethereum blockchain. This testnet behaves very similarly to the real blockchain (mainnet), but does not require real ETH to pay for transactions.

### 1. Installer Metamask

**1.1** Allez sur <0>metamask.io</0>.

**1.2** Click on the download button, then click on install for your browser (e.g. Chrome) and add the extension to your browser.

**1.3** Create a wallet as described.

### 2. Obtenir un jeton testnet

In order to make transactions on the testnet we need Ethereum testnet tokens, which you can receive from something called a _faucet_.

**2.1** Switch your Metamask network by clicking on the "Ethereum Mainnetwork" drop down and selecting "Ropsten Test Network". If you don’t see any test networks, click on the "Show/hide" link and enable "Show test networks" in the settings.

**2.2** Allez sur <a href="https://faucet.paradigm.xyz/" target="_blank">https://faucet.ropsten.be/</a>, entrez l'adresse de votre compte et réclamez testnet ETH. Vous pouvez également utiliser d'autres robinets en ropsten comme <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">https://faucet.paradigm.xyz/</a> ou <1>https://app.mycrypto.com/faucet</1>. Jetez un coup d'œil aux robinets répertoriés sur <0>ethereum.org</0> pour en savoir plus.

### 3. Déploiement

Assurez-vous que le contrat EduCoin est compilé.

**3.1.** In the "DEPLOY & RUN TRANSACTIONS" module of the Remix IDE under "ENVIRONMENT" select "Injected Web3". It will ask you to connect your account which you should confirm.

**3.2** Deploy the EduCoin contract and confirm the transaction in Metamask.

**3.3** Your contract should appear in the "Deployed Contracts" section. Copy the contract address.

**3.4** In Metamask, click on assets, then click on the "Import tokens" link, and paste the address of your contract in the input field.

You should now see a balance of 1000 EDC in your wallet.

### 4. Effectuer une transaction

**4.1** Cliquez sur l'identification (représentation visuelle de votre adresse) dans le portefeuille Metamask et créez un deuxième compte (Compte 2).

**4.2** Copy the address of Account 2.

**4.3** Switch to the first account (Account 1) and send 250 EDC to Account 2. Check the balances of Account 1 and Account 2. Vous devrez peut-être rajouter l'adresse du jeton pour que le compte 2 importe les jetons et vous aurez besoin de testeth si vous voulez effectuer une transaction avec ce compte.

Vous pouvez également voir les soldes de votre compte si vous regardez le contrat dans Remix et appelez la fonction `balanceOf` en utilisant les adresses du compte 1 et du compte 2.
