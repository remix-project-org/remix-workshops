For dis section, we go use Metamask (one Ethereum wallet) to take deploy our contract go one testnet of di Ethereum blockchain. Dis testnet dey behave like di real blockchain (mainnet), but e no need real ETH to pay for transactions.

### 1. Go install Metamask

**1.1** Dey go <a href="https://metamask.io/" target="_blank">metamask.io</a>.

**1.2** Click di download button den click install for your browser like now Chrome and put di extension for your browser.

**1.3** Create wallet as dem talk am.

### 2. Go carry testnet token

To fit make transaction for di testnet we go need Ethereum testnet token wey you fit receive from something wey dem dey call _faucet_.

**2.1** On your metamask network make you click for "Ethereum Mainnetwork" go down make you dey select "Ropsten Test Network". If you no see any test networks click di “Show/hide” link come enable “Show test networks” inside di settings.

**2.2** Go <a href="https://faucet.ropsten.be/" target="_blank">https://faucet.ropsten.be/</a>, make you enter di address for your akant come claim testnet ETH. You fit dey use oda ropsten faucets like dem <a href="https://faucet.paradigm.xyz/" target="_blank"> https://faucet.paradigm.xyz/</a> or <a href="https://app.mycrypto.com/faucet" target="_blank">https://app.mycrypto.com/faucet</a>. Go look di faucets wey dem list for <a href="https://ethereum.org/en/developers/docs/networks/#testnet-faucets" target="_blank">ethereum.org</a> to take sabi more.

### 3. Deploymet

Make sure say di EduCoin contract dey compiled.

**3.1.** FOR DI "DEPLOY & RUN TRANSACTIONS" module of the Remix IDE under "ENVIRONMENT" go select "Injected Web3". E go ask you to connect your akant make sure say you confirm am.

**3.2** Deploy di EduCoin contract make you confidant di transaction for Metamask.

**3.3** your contrakt suppose show for di deployed contrakt place. Copi di contrakt adress.

**3.4** For metamask click asset den go click Import token link come paste di adress for your contrakt for di input field.

You go come see balance of 1000 EDC for your wallet.

### 4. Do transaction

**4.1** Click di identicon (voictire representation of your address) inside di Metamask wallet make you come create second account (Account 2).

**4.2** Copy di address of Account 2.

**4.3** Switch go di first account (Account 1) make you send 250 EDC go Account 2. Check di balance of Akant 1 and Akant 2. You fit need put di token address again for Account 2 for import di tokens and you go need testeth if you wan make transaction with dis account.

You fit also see your account balances if you look at di contract inside Remix and call di balanceOf function wey dey use di addresses of Account 1 and Account 2.
