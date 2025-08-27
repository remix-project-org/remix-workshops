For this part, we go use metamask( na Ethereum wallet) take deploy our contract go sepolia testnet for Ethereum blockchain, mint NFT, con look the NFT for opensea Marketplace.

### 1. Download metamask

**1.1** Dey go <a href="https://metamask.io/" target="_blank">metamask.io</a>.

**1.2** Click di download button den click install for your browser like now Chrome and put di extension for your browser.

1.3 make the wallet as we talk am.

### 2. Collect testnet token for sepolia

To do transaction for testnet, we gats get Ethereum testnet tokens.

2.1\*\* change your Metamask from "Ethereum Mainnetwork" go "Sepolia Test Network".

2.2\*\* Go to <a href="https://www.alchemy.com/faucets/ethereum-sepolia" 
target="_blank">https://www.alchemy.com/faucets/ethereum-sepolia</a>, write the address of your own account con claim testnet ETH.
Or observe the faucets listed for <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">ethereum.org</a> for plenty options.

### 3. How to deploy contract

**3.1** In the "DEPLOY & RUN TRANSACTIONS" module of the Remix IDE under "ENVIRONMENT" **select** "Injected Provide-Metamask" (or whatever wallet you are using). E go come ask you make u connect your account wey u go confirm. Then inside the wallet connect go sepolia network.  You go gats turn on switch to see test networks. Once connected, there will be a "badge" with Sepolia and its network ID under "Injected Provider".

**3.2** Deploy your token contract and confirm the transaction in Metamask.

**3.3**  Your contract should appear in the "Deployed Contracts" section.

### 4. Mint an NFT

**4.1** Expand your contract in the IDE so you can see the buttons for the functions.

**4.2** Expand the input fields next to the safeMint button. Enter the Ethereum address of the account that is connected to Remix in the “to:” input field. Enter “0” in the input field "tokenID:". Click on transact.

**4.3** In Metamask click on assets, then click on the “Import tokens” link, and paste the address of your contract in the input field. You can set decimals to 0.

You should now see the name of the symbol of your token contract (e.g. GEO) in your “Assets” view in Metamask. You should have one of these tokens.

### 5. Observe your nft for opensea

<a href="https://opensea.io/" 
target="_blank">OpenSea </a> is one of the most popular online marketplace for NFTs. OpenSea also provides a version where you can see assets on the testnet, under <a href="https://testnets.opensea.io/" 
target="_blank">https://testnets.opensea.io/</a>

**5.1** Go to <a href="https://testnets.opensea.io/login" 
target="_blank">https://testnets.opensea.io/login</a>.

5.2 link your Metamask wallet. You should be redirected to your account <a href="https://testnets.opensea.io/account" target="_blank">https://testnets.opensea.io/account</a> view on OpenSea, where you should be able to see your NFT. You suppose see the picture of your nft, when you tap am. You go see the name, description and hidden properties, and the attribute wey you create too.

If you don finally finish this course and you dey familiar with basis for solidity development, we go encourage you make you no stop your learning journey based on learning how to make your own NFT auction contract wey dey the Learneth resources.