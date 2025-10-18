Di Axelar executable get important helper functions wey go dey automatically executed for di final place chain in correspondence to di important inbound transaction from di source chain.

Di following na di important functions wey you go need to use from Axelar Executable

## \_execute()

Dis function dey handle di execution for di final place chain. E dey take di following four parameta:

1. `commandId`: Na unique transaction id dor Di Axelar chain.
2. `sourceChain`: Di blockchain wey dem send di transaction from
3. `sourceAddress`: Di address from di source chain wey di transaction dey sent from
4. `payload`: Di message wey dem send

Di sourceChain and sourceAddress na key parameters wey you dey receive out of di box wey fit dey use to dey verify authenticity of messages for di final place chain. Di payload like wey we don talk for di gateway section na di message wey dem send from di source chain wey dem go dey use for your final place chain. Di `commandId` no go dey used for di rest of dis module.

## \_executeWithToken()

Dis function dey handle di execution for di final place chain for message wey dem dey send with fungible token. E dey take six important parameta:

1. `commandId`: Na unique transaction id for di Axelar chain.
2. `sourceChain`: Di blockchain wey dem send di transaction from
3. `sourceAddress`: Di address from di source chain wey dem send di transaction from
4. `payload`: Di message wey dem sent
5. `tokenSymbol`: Di symbol of the token wey dem send
6. `amount`: Di amount of dat token wey dem send

Di first four parameta resemble di `_execute()` function. Di final two parameters of tokenSymbol and amount dey in reference to di token wey dem send join di message. E go gree you for di final place chain to relate with di token accordingly like now to transfer am for anoda receiving address. Di commandos no go dey used for di rest of di module.
