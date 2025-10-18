## To fit query di blockchain

For dis tutorial, we go run di script wey queries blockchain using javascript library.

Dis one means say instead of using di remix GUI orr a block explorer like Etherscan we go use script for di editor or ruun am from terminal.

Di js libraries wey dey use di most interacting with di blockchain na web3.js and ether.js.

Make we begin with simple web3.js example, queryBlockNum.js.

Di script call to web3.js e wrapped in self executing async function wey contain try/catch block.

We query di current blocknumber with
let blockNumber = await web3.eth.getBlockNumber()\`

Know say di object web3 dey injected by remix. For more info on web3.js, check di docs, <a href="https://web3js.readthedocs.io/" target="_blank">https://web3js.readthedocs.io</a>.

To use web.3js or ether.js u need to select di **Injected Web3** or **Web3 Provider** environment in the **Deploy & Run** module.  Script no dey currently work with di JSVM. **if u try, u go get error.**

For example choose **Injected Web3** for di deploy and run module and metamask installed.

For di terminnal, execute `remix.executed()`. Dis command fit remove di current javascript file with di line `let blockNumber= await web3.eth.getblockNumber()`.

Di console, u fit see di current block number of di chain dat metamask dey connected.
