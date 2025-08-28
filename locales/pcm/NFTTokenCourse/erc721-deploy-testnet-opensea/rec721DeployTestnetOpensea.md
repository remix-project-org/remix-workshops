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

**3.1** For di "DEPLOY & RUN TRANSACTIONS" module of di Remix IDE under "ENVIRONMENT" **select** "Injected Provide-Metamask" (or Any kin wallets wey u dey use). E go come ask you make u connect your account wey u go confirm. Then inside the wallet connect go sepolia network.  You go gats turn on switch to see test networks. Once connected one kind badge with sepolia and it's network ID under injected provider.

**3.2** Deploy your token contract make you confirm di transaction for Metamask.

**3.3**  Your contract suppose  appear for di "Deployed Contracts" section.

### 4. Mint NFT

**4.1** Expand ur contract inside the IDE so u go fit see the buttons for the functions.

**4.2** Expand the input fields next to the safeMint button. Enter di ethereum address of the account wey dey connected to remix in the to input field. Enter “0” inside the input field "tokenID:". Click on transact.

**4.3** Inside Metamask click on assets, then click that “Import tokens” link, and paste the address of ur contract inside the input field. U fit set did decimals go 0.

You suppose don see the name of di symbol of your token contract (e.g. GEO) in your Assets view for Metamask. You suppose don get one of these token.

### 5. Observe your nft for opensea

<a href="https://opensea.io/" 
target="_blank">OpenSea </a> na one of di most popular online marketplace for NFTs. OpenSea dey provides a version where you fit take see assets for the testnet, under <a href="https://testnets.opensea.io/" 
target="_blank">https://testnets.opensea.io/</a>

**5.1** Go to <a href="https://testnets.opensea.io/login" 
target="_blank">https://testnets.opensea.io/login</a>.

5.2 link your Metamask wallet. Dem suppose carry you go back to your account <a href="https://testnets.opensea.io/account" target="_blank">https://testnets.opensea.io/account</a> view on OpenSea, where you suppose take see your NFT. You suppose see the picture of your nft, when you tap am. You go see the name, description and hidden properties, and the attribute wey you create too.

If you don finally finish this course and you dey familiar with basis for solidity development, we go encourage you make you no stop your learning journey based on learning how to make your own NFT auction contract wey dey the Learneth resources.