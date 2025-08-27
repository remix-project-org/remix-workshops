Di Axelar Gateway na di entrypoint wey your smart contract take enter inside di Axelar ecosystem. Once you don trigger di correct function for di Gateway, your transaction go start im interchain journey from your source chain waka pass di Axelar network reach di destination chain. Each chain wey dem connected to Axelar get gateway wey dem deploy gateway contract wey you fit use relate with.

Di following na di two more important functions wey you go need to sabi.

## callcontract ()

Dis function dey trigger one interchain transaction with message from di source go di chain destination. E go take three parameta wey dey important:

1. `destinationChain`: Di name of di destination chain
2. `destinationContractAddress`: Di address for di destination chain dis transaction go execute at.
3. `payload`: Di message wey dem send

Di first two parameta dey intuitive. Dem consist of both di name of di chain wey you wan make dis transaction go, and di address for dat chain wey you wan end execute for. Dis final parameta na di payload. Dis payload represent general message wey dem send go di chain final place. Dem fit use di message for different ways for di destination chain. Like now, you fit send data wey dem go use as parameter inside another function for di final place chain, you fit send function signature as message wey go later execute for di final place chain, and plenty other tins.

## callContractWithToken()

Dis function dey trigger one interchain transaction with message from di source go di chain destination. "E dey take five important parameters:"

1. `destinationChain`: Di name of di destination chain
2. `destinationContractAddress`: Di address for di destination chain dis transaction go execute at.
3. `payload`: Di message wey dem send
4. di symbol\`: de symbol of de token wey dem send
5. `amount`: Di amant of dat token wey dem send

Di first three parameta for here na di same as e be for `callContract()`. Di final two parameters dey important to di token wey dem dey send join wit di message. Dis na di symbol of di token and di amount of di token wey dem send.
