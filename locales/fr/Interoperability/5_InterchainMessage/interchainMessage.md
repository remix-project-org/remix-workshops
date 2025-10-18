Dans cette section, nous allons créer un contrat qui enverra un message "bonjour le monde" entre deux blockchains.

## Constructor

The first thing you will need to create is the `constructor` for the function. This will allow you to set the `Gateway` and `Gas Service` contracts we discussed in the previous sections.

When deploying the contract you will pass in the address of the `Gateway` and `GasService` for Ethereum Sepolia those addresses are `0xe432150cce91c13a887f7D836923d5597adD8E31` for the Gateway and `0xbE406F0189A0B4cf3A05C286473D23791Dd44Cc6` for the Gas Service.

Pour la liste complète des adresses Axelar pertinentes
<0>see here</0>

## Envoyer un message interchaîne

Now that the constructor has set the relevant Axelar addresses needed to trigger an interchain transaction you can move on to the `setRemoteValue()`, which will trigger this transaction.

This function takes three parameters:

1. `_destinationChain` : La chaîne à laquelle la transaction va
2. `_destinationAddress` : L'adresse sur la chaîne de destination à laquelle la transaction sera exécutée
3. `_message` : Le message transmis à la chaîne de destination

First, you have a `require` statement which ensures that the `msg.value` contains a value. This `msg.value` will be used to pay the `GasService`. If no funds were sent, then the transaction should be reverted as the transaction cannot execute on the Axelar blockchain and destination chain without any gas.

Ensuite, vous codez le `_message` qui a été transmis. Notez que le `_message` est défini comme un type `string`. Axelar expects this message to be submitted as a `bytes` type so to convert the `string` to `bytes` you simply pass it through `abi.encode()`.

Maintenant, avec votre message codé, vous pouvez commencer à interagir avec le `GasService` et le `Gateway`

To pay for the entire interchain transaction you will trigger the function `payNativeGasForContractCall`, which is defined in the `GasService`.

This function needs the parameters explained earlier in the GasService section. L'expéditeur de cette transaction sera ce contrat, qui est `adresse(ceci)`. The `destinationChain` and `destinationAddress` can simply be passed in from this functions parameters, the `payload` is the encoded \_message we wrote earlier. Enfin, vous devez spécifier quelle est l'adresse de remboursement, cela peut être l'adresse qui déclenche cette fonction, que vous obtenez en écrivant `msg.sender`.

Once you trigger this function you will have successfully sent a transaction from the source chain via Axelar to the destination chain! Mais il y a encore une dernière étape qui doit être accomplie.

### Recevoir un message sur la chaîne de destination

Sur la chaîne de destination, la transaction interchaîne entrante doit être captée et gérée par la fonction `_execute()` de `AxelarExecutable`.

La fonction `_execute()` est définie dans le contrat `AxelarExecutable`, donc lors de la définition de cette fonction, vous devez vous rappeler d'inclure le mot-clé `override`.

This function takes three parameters.

1. `_sourceChain`: The blockchain which the transaction has originated from
2. `_sourceAddress` : L'adresse de la chaîne source à partir de laquelle la transaction a été envoyée
3. `_payload` : Le message qui a été envoyé à partir de la chaîne source

The first thing that needs to be done in this contract is to get access to your `message` that was sent. Recall, before sending the message it was sent through `abi.encode()` to convert the message from type `string` to type `bytes`. To convert your message back from type `bytes` to type `string` simply pass the `_payload` to the function `abi.decode()` and specify that you want the `_payload` decoded to type `string`. This will return the message as a string.

Maintenant que vous avez votre message comme chaîne de type, vous pouvez définir les variables de stockage `sourceChain` et `sourceAddress` comme `_sourceChain` et `_sourceAddress` pour avoir une référence facile aux données qui ont été transmises. You can also emit the `Executed` event with the `sourceAddress` and `message` event that you just decoded.

Super! À ce stade, vous gérez maintenant la transaction interchaîne sur la chaîne de destination.

Pour interagir avec ce contrat, assurez-vous de le déployer sur au moins deux blockchains afin de pouvoir appeler `setRemoteValue()` à partir d'une chaîne, puis de déclencher automatiquement la fonction `_execute()` sur une autre chaîne. You will be able to query the `sourceChain` and `sourceAddress` variables on the destination chain to ensure that the interchain execution worked correctly.

Pour voir l'intégralité de l'étape par étape de la transaction interchaîne, consultez l'explorateur de blocs <0>Axelarscan (testnet)</0>.
