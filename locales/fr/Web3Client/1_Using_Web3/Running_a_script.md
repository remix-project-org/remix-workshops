## Interroger la Blockchain

Dans ce tutoriel, nous allons exécuter un script qui interroge la blockchain à l'aide d'une bibliothèque JavaScript.

Cela signifie qu'au lieu d'utiliser l'interface graphique Remix ou un explorateur de blocs comme Etherscan, nous utiliserons un script dans l'éditeur et l'exécuterons à partir du terminal.

The JS libraries that are used the most for interacting with the blockchain are web3.js & ethers.js.

Commençons par un simple exemple web3.js, queryBlockNum.js.

The script's call to web3.js is wrapped in a self-executing async function that contains a try/catch block.

Nous interrogerons le numéro de bloc actuel avec :
`let blockNumber = await web3.eth.getBlockNumber()`

Note that the object `web3` is injected by Remix. Pour plus d'informations sur web3.js, consultez leurs documents, <0>https://web3js.readthedocs.io</0>.

To use web3.js or ethers.js, you need to select the **Injected Web3** or **Web3 Provider** environment in the **Deploy & Run** module.  Scripts don't currently work with the JSVM. **If you try, you'll get an error.**

So for this example choose **Injected Web3** in the Deploy & Run module and have Metamask installed.

Depuis le terminal, exécutez `remix.execute()`. Cette commande exécutera le fichier JavaScript actuel avec la ligne `let blockNumber = await web3.eth.getBlockNumber()`.

In the console, you should see the current block number of the chain that metamask is connected to.
