In this section, we will use Metamask (an Ethereum wallet) to deploy our contract to the Sepolia testnet of the Ethereum blockchain, mint an NFT, and look at it on the NFT marketplace OpenSea.

### 1. Install Metamask

**1.1** Allez sur <0>metamask.io</0>.

**1.2** Click on the download button, then click on install for your browser (e.g. Chrome) and add the extension to your browser.

**1.3** Create a wallet as described.

### 2. Get testnet token for Sepolia

In order to make transactions on the testnet, we need Ethereum testnet tokens.

**2.1** Switch your Metamask from "Ethereum Mainnetwork" to "Sepolia Test Network".

**2.2** Allez sur <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">https://www.alchemy.com/faucets/ethereum-sepolia</a>, entrez l'adresse de votre compte et réclamez testnet ETH.
Ou consultez les robinets répertoriés sur <0>ethereum.org</0> pour d'autres options.

### 3. Déploiement contractuel

**3.1** In the "DEPLOY & RUN TRANSACTIONS" module of the Remix IDE under "ENVIRONMENT" **select** "Injected Provide-Metamask" (or whatever wallet you are using). It should then ask you to connect your account, which you should confirm. Then in the wallet, connect to the Sepolia network.  You may need to turn on a switch to view test networks. Once connected, there will be a "badge" with Sepolia and its network ID under "Injected Provider".

**3.2** Deploy your token contract and confirm the transaction in Metamask.

**3.3**  Your contract should appear in the "Deployed Contracts" section.

### 4. Mint an NFT

**4.1** Développez votre contrat dans l'IDE afin de pouvoir voir les boutons pour les fonctions.

**4.2** Expand the input fields next to the safeMint button. Enter the Ethereum address of the account that is connected to Remix in the “to:” input field. Enter “0” in the input field "tokenID:". Cliquez sur la transaction.

**4.3** In Metamask click on assets, then click on the “Import tokens” link, and paste the address of your contract in the input field. You can set decimals to 0.

Vous devriez maintenant voir le nom du symbole de votre contrat de jeton (par exemple GEO) dans votre vue "Actifs" dans Metamask. You should have one of these tokens.

### 5. Voir votre NFT sur OpenSea

<a href="https://testnets.opensea.io/" 
target="_blank">OpenSea </a> est l'un des marchés en ligne les plus populaires pour les TVN. OpenSea fournit également une version où vous pouvez voir les actifs sur le testnet, sous <a href="https://testnets.opensea.io/login" 
target="_blank">https://testnets.opensea.io/</a>

**5.1** Allez sur <0>https://testnets.opensea.io/login</0>.

**5.2** Connect with your Metamask wallet. Vous devriez être redirigé vers votre compte <0>https://testnets.opensea.io/account</0> vue sur OpenSea, où vous devriez pouvoir voir votre NFT. You should see the image of your NFT; when you click on it, you should see the name, description, and under properties, also the attributes that you created.

If you successfully completed this course and are familiar with the basics of Solidity development, we encourage you to continue your learning journey by learning how to create your own NFT auction contract from the Learneth resources.