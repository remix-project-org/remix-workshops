As we have seen in the previous section, executing code via transactions on the Ethereum Network costs transaction fees in the form of Ether. Le montant des frais qui doivent être payés pour exécuter une transaction dépend de la quantité de _gaz_ que l'exécution de la transaction coûte.

### Gas

_Gas_ is the unit that measures the amount of computational effort that is required to execute a specific operation on the Ethereum network.

### Prix du gaz

Le _gaz_ qui alimente Ethereum est parfois comparé au gaz qui alimente une voiture. La quantité d'essence que votre voiture consomme est à peu près la même, mais le prix que vous payez pour l'essence dépend du marché.

De même, la quantité de _gaz_ dont une transaction a besoin est toujours la même pour le même travail de calcul qui lui est associé. Cependant, le prix que l'expéditeur de la transaction est prêt à payer pour le _gaz_ lui incombe. Transactions with higher _gas prices_ are going through faster; transactions with very low _gas prices_ might not go through at all.

When sending a transaction, the sender has to pay the _gas_ fee (gas_price \* gas) upon execution of the transaction. If _gas_ is left over after the execution is completed, the sender gets refunded.

_Gas_ prices are denoted in gwei.

### Gas limit

When sending a transaction, the sender specifies the maximum amount of gas that they are willing to pay for. If they set the limit too low, their transaction can run out of _gas_ before being completed, reverting any changes being made. In this case, the _gas_ was consumed and can’t be refunded.

En savoir plus sur _gas_ sur <a href="https://www.youtube.com/watch?v=oTS9uxU6cAM" target="_blank">ethereum.org</a>.

<a href="https://www.youtube.com/watch?v=oTS9uxU6cAM" target="_blank">Regardez un tutoriel vidéo sur le gaz et le prix de l'essence</a>.

## ⭐️ Affectation

Create a new `public` state variable in the `Gas` contract called `cost` of the type `uint`. Store the value of the gas cost for deploying the contract in the new variable, including the cost for the value you are storing.

Tip: You can check in the Remix terminal the details of a transaction, including the gas cost. You can also use the Remix plugin _Gas Profiler_ to check for the gas cost of transactions.