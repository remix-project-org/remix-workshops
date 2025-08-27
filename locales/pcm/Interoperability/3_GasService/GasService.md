Axelar Gas Service na important tool wey fot help us pay moni for transaction from one chain to anoda. E dey allow make you pay for the transaction with the token of the chain wey you dey transact from, make user (and developer) experience for no get wahala. If di siurce chain na Ethereum, and where we the chain you wan send am go na Polygon. Na Ethereum you go use pay for all the service and you no need use matic at all take pay for the Polygon chain wey you wan send am go.

"Di two relevant functions wey you need sabi for Gas Service na dis ones.

## u go payNativeGasForContractCall()

"Dis function go allow you pay for di whole interchain transaction with di native token of di source chain. "E dey take five important parameters:"

1. "sender: Na di address wey dey make di payment
2. `destinationAddress`: Di adress for di destination chain transaction go execute for
3. `destinationAddress`: Di adress for di destination chain transaction go execute for
4. `payload`: Di message wey dem send
5. na di `refundAddress`: de address any refunds should be sent to if too much gas was sent along with dis transaction.

Di parameters dey overlap with di ones wey callContract() function for Gateway contract need. Di two parameters no discuss for dey gateway area are `sender` and `refundAddress`. Di sender na di address wey dey pay for di transaction, and di refund address na di address wey go receive any extra funds wey dem send to di gas service.

## u go payNativeGasForContractCallWithToken()

"Dis function go allow you pay for di whole interchain transaction (wey include token transfer) with di native token of di source chain. "E dey take five important parameters:"

1. "sender: Na di address wey dey make di payment
2. `destinationAddress`: Di adress for di destination chain transaction go execute for
3. `destinationAddress`: Di adress for di destination chain transaction go execute for
4. `payload`: Di message wey dem send
5. di symbol\`: de symbol of de token that was sent
6. di symbol\`: de symbol of de token that was sent
7. na di `refundAddress`: de address any refunds should be sent to if too much gas was sent along with dis transaction.

Dis function dey nearly identical to di first top one di main difference being dat e use for di message + token transfertransactions as opposed to just interchain message transaction (aka GMP Transactions). As a result di gasservice needs also di `symbol` and `amount` of di token that is being sent.
