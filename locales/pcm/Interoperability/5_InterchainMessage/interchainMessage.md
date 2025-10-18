For dis section we go create contract wey go send hello world give two blockchain.

## Di constructor

Di first in to do na to crate di constructor for di work. E go allow makenyou set gateway and gas service contract as discuss for oda section.

Wen you dey deploy contract you go pass di adress of di gateway and gas service for Ethereum Sepolia dose adress dem be 0xe432150cce91c13a887f7D836923d5597adD8E31`for di Gateway and`0xbE406F0189A0B4cf3A05C286473D23791Dd44Cc6\` for di Gas Service.

For di full list of di relevant Axelar address <a href="https://docs.axelar.dev/resources/contract-addresses/testnet" target="_blank">check here</a>

## Send message wey dey interchain

Now wey di constructor don set di relevant Axelar address wey e need to take trigger interchain transaction you fit move dey go `setRemoteValue()`, wey go trigger dis transaction.

Di function dey take three parameta:

1. `_destinationChain`: Di chain ey di transation dey go
2. `_destinationAddress`: Di adress for di destination chain transaction go execute for
3. `_message`: Di message wey dem pass go di destination chain

First you go need statement wey dey ensure say di `msg.value` get value. Dis msg.value`dem go use am pa`GasService\`. If dem no send moni den di transaction go go back as di transaction no fit execute for Alexar blockchain and destination chain wey gas no dey.

Next you go encode di message wey dem pass. You o notice say di message na set of string type. Alexar dey expect say dis message dem go submit am as bytes type so to take convert di string go bytes you go simply pass am through `abi.encode()`.

Now wey your gas don encode you go start to dey follow gas sevice and di gateway talk

To pay for di entire interchain transaction you go trigger di function `payNativeGasForContractCall`, wey dem define for gas service.

Dis function need di parameter wey dem explain for start in di GasService section. Di sender for dis transaction dey dis contract, wey be address(dis)'. Di destination chin and di destination adress dem fit pass am from dis function parameters di payload na di encoded message wey we write before. Last last you go need specify wetin di refund adress be e fit be di adress wey dey trigger dis function wey you go get as you dey write `msg.sender`.

Once you trigger dis function you don successfully send transaction from di source chin through Alexar go di destinaton chain! But one step dey wey person go need complete.

### Make you collect emssage for destination chain

For di destination chain di inbound interchain transaction dem need to pick am up make `AxelarExecutable`'s `_execute()` function handle am.

Di `_execute()` function im meaning dey for `AxelarExecutable` contract so wen you dey define dis function you go remember say you go need include di override keyword.

Di function dey take three parameta.

1. `_sourceChain`: The blockchain wey di transaction come from
2. `_sourceAddress`: Di address for di source chain ey dem send di transaction from
3. `_payload`: Dem don send di message from di source chain

Di first thing ey you go need do for dis contract na to get access to your message wey dem send. Remember, before you send di message dem send am through `abi.encode()`to turn di message from type string to type bytes. To turn di message back frm type bytes go type string just pass di overload go di function abi decode am come secify say you want di payload make e decode go back string. E go return di message as string.

Now wey you don get your message as type string you fit set di `sourceChain`and `sourceAddress` storage variable as `_sourceChain` and `_sourceAddress` to fit get reference give di data wey dem pass come. You fit commot di `Executed` event wit di `sourceAddress` and `message` event wey you just decode.

Make sense! Like dis now you dey handle di interchain for destination chain.

To fit relate wit dis contract make sue say you deploy am for at least two blockchain so you go call `setRemoteValue()` from di one chain and den have di `_execute()` function wey go just trigger from anoda chain. You go fit query di `sourceChain` and `sourceAddress` variables for di destination chain to make sure say di interchain execution work well well.

To fit see di full step of di interchain transaction go check di <a href="https://testnet.axelarscan.io" target="_blank">Axelarscan (testnet) block explorer</a>.
