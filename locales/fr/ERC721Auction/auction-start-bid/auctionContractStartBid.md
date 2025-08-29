In this section, we will create a function to start the auction and a function to bid on the NFT.

### Start

Nous utilisons certaines structures de contrôle pour vérifier si les conditions nécessaires sont remplies avant de laisser le vendeur commencer la vente aux enchères.

Tout d'abord, nous vérifions si la vente aux enchères a déjà commencé (ligne 49). If it has started and our state variable `started` returns `true` we exit the function and throw an exception.

The second condition we check for is whether the seller is executing the function (line 50). We have already created a function to store the seller's address when they deploy the contract in the `seller` state variable and can now check if the account executing the start function is the seller. If not we throw an exception.

Next, we want to transfer the NFT that is up for auction from the seller to the contract (line 52).
We set the state variable `started` to `true` (line 53), and create an end date for the auction (line 54). In this case, it will be seven days from when the start function has been called. We can use a suffix like `days` after a literal number to specify units of time. Si vous voulez en savoir plus sur les unités de temps, jetez un coup d'œil à la <a href="https://docs.soliditylang.org/en/latest/units-and-global-variables.html#time-units" target="_blank">documentation de solidité</a>.

Enfin, nous émettrons notre événement `Start()` (ligne 56).

### Bid

Avant que l'appelant de la fonction puisse faire une offre, nous devons nous assurer que certaines conditions sont remplies. L'enchère doit avoir commencé (ligne 60), l'enchère ne peut pas avoir pris fin (ligne 61) et l'offre (la valeur attachée à l'appel) doit être supérieure à l'offre la plus élevée actuelle (ligne 62).

Maintenant, nous voulons stocker l'enchère du plus offrant actuel avant de faire une nouvelle offre.
First, we check if there is a bidder (line 64). If this function call is the first bid then the next line would be irrelevant.
In our mapping `bids` (line 34) we map the key, the `address` of the bidder, to the value, a `uint` that represents the total amount of ETH a bidder has bid in the auction before withdrawing.
S'il y a un enchérisseur, nous ajoutons la dernière offre (`highestBid`) du `highestBidder` à la valeur totale des offres qu'ils ont faites (ligne 65) avant de retirer.
We store the bids because we want to enable the bidder to withdraw the ETH they used to make bids if they are no longer the highest bidder.

Next, we set the `highestBidder` to the account calling the function (line 68), and the `highestBid` to their bid, the value that was sent with the call (line 69).

Finally, we emit the `Bid` event (line 71).

## ⭐️ Assignment

1. Deploy an NFT contract. You can use the NFT contract that we create in our "Solidity NFT Course" Learneth course.

2. Mint yourself an NFT with the tokenId 0.

3. Deploy this EnglishAuction contract. Utilisez l'adresse du contrat NFT comme argument pour le paramètre `_nft`, 0 pour `_nftId` et 1 pour `_startingBid`.

4. Call the `approve` function of your NFT contract with the address of the auction contract as an argument for the `to` parameter, and 0 for `tokenId`. This will allow the contract to transfer the token to be auctioned.

5. Call the `start` function of your auction contract. Si vous appelez la fonction `démarré` maintenant, elle devrait renvoyer `true`. If you call the `highestBid` function it should return 1.

6. Définissez la valeur que vous pouvez attacher aux transactions sur 3 Wei et appelez la fonction `enchère` du contrat d'enchères. If you call the `highestBid` function it should now return 3.