At dis point we fit don gomover an example of how to fit send general message
between one blockchain to another. Now make we implement contract wey go send message and token from one blockchain to another.

## Di overview

Dis contract fit dey large and familiar. For di other area constructor dey recieve im gateway and `Gas Service` addresses.

E get function wey dem go call from di source chain wey dem call`sendToMany` that takes in parameters similar to de previous section.

1. u fit`_destinationChain`: The chain de transaction is sending to
2. `_destinationAddress`: Di adress for di destination chain transaction go execute for
3. u fit`_destinationAddresses`: The message that you will be sending along with your token transfer. For di message is a list of receiving addresses for di token transfer.
4. dis `_symbol`: die symbol of de token address being sent
5. di `_amount`: de amount of di token being sent

For dis function we get di require statement implemented to ensure gas

We get di basic ERC20 functionality to fit send di token from di call wallet to dis smart contract. Di contract dem dey call am di `approve` function to allow de Gateway to eventually transfer funds on its behalf.

Finally di `_executeWithToken()` function is also implemented out of de box.

E fit makes use the following params:

1. dis `_payload`: de incoming message from the source chain
2. di_tokenSymbol\`: The symbol of the token that was sent from the source chain
3. De `_amount`: The amount of the token that was sent from the source chain

Now dis param dem pass di executed()\` function can send the tokens that were sent to the appropriate receivers.

## Problem

Ur challenge here na to finish di `sendToMany()` function using the Axelar Gateway and Gas Service to trigger an interchain transaction.

For di end u go dey able to fit deploy dis contract on two testnets, trigger di `sendToMany()` function and see de live transaction on <a href="https://testnet.axelarscan.io" target="_blank">Axelarscan (testnet) block explorer</a>.

### Di testing notes

Note say for dis one e dey recommended for ERC20 to fit use im USDC`a wrapped version of the USDC token that can be obtained from <a href= "https://docs.axelar.dev/resources/rpc/resources" target="_blank">the discord faucet bot</a>.
 When u trigger di`sendToMany()`function simply pass in de symbol`aUSDC\` to de fourth param.

Note say for dis one when u trigger di `sendToMany()` function you must remember to `approve` ur contract to spend `aUSDC` tokens on your behalf, otherwise `transferFrom()` on line49 will throw an error.
