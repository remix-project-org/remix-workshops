At dis point we fit don gomover an example of how to fit send general message
between one blockchain to another. Now make we implement contract wey go send message and token from one blockchain to another.

## Di overview

Dis contract fit dey large and familiar. For di other area constructor dey recieve im gateway and `Gas Service` addresses.

E get function wey dem go call from di source chain wey dem call`sendToMany` that takes in parameters similar to de previous section.

1. u fit`_destinationChain`: The chain de transaction is sending to
2. `_destinationAddress`: Di adress for di destination chain transaction go execute for
3. u fit`_destinationAddresses`: The message that you will be sending along with your token transfer. For di message is a list of receiving addresses for di token transfer.
4. `_symbol`: The symbol of the token address being sent
5. `_amount`: The amount of the token being sent

In the function we already have the `require` statement implemented to ensure gas is sent

We also have the basic ERC20 functionality to send the token from the calling wallet to this smart contract. The contract also calls the `approve` function to allow the Gateway to eventually transfer funds on its behalf.

Finally, the `_executeWithToken()` function is also implemented out of the box.

It makes use of the following params:

1. `_payload`: The incoming message from the source chain
2. `_tokenSymbol`: The symbol of the token that was sent from the source chain
3. `_amount`: The amount of the token that was sent from the source chain

Now with these params that were passed in, the `_execute()` function can send the tokens that were sent to the appropriate receivers.

## Challenge

Your challenge here is to finish off the `sendToMany()` function using the Axelar Gateway and Gas Service to trigger an interchain transaction.

In the end you should be able to deploy this contract on two testnets, trigger the `sendToMany()` function and see the live transaction on <a href="https://testnet.axelarscan.io" target="_blank">Axelarscan (testnet) block explorer</a>.

### Testing Notes

Note 1: The recommended ERC20 to use is `aUSDC` a wrapped version of the USDC token that can be obtained from <a href= "https://docs.axelar.dev/resources/rpc/resources" target="_blank">the discord faucet bot</a>. When triggering the `sendToMany()` function simply pass in the symbol `aUSDC` to the fourth param.

Note2: When triggering the `sendToMany()` function you must remember to `approve` your contract to spend `aUSDC` tokens on your behalf, otherwise `transferFrom()` on line49 will throw an error.
