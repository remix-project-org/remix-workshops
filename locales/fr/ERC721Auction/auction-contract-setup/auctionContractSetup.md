In this contract tutorial, we will learn how to create an ERC721 (NFT) auction contract.
We recommend to you, to do the Learneth "Solidity NFT Course" before starting this tutorial.

In the following sections, we will create a contract that will enable a seller to auction an NFT to the highest bidder. Ce contrat a été créé par le projet <0>Solidity by Example</0>. In this first section, we will create an interface, the necessary state variables, and the constructor.

### Interface

Nous créons l'interface (ligne 5) pour le jeton ERC721 puisque notre contrat devra interagir avec lui. Nous aurons besoin des méthodes `safeTransferFrom` (ligne 5) et` transferFrom` (ligne 11).

### EnglishAuction

Nous créons les quatre événements `Start`, `Bid`, `Withdraw`, `End` (ligne 19-22) afin de pouvoir enregistrer les interactions importantes.

Next, we will create the state variables that store all the necessary information about our auction on-chain.

We create two state variables for the NFT we want to auction. Dans la variable `nft` (ligne 24), nous stockons une représentation du contrat NFT, qui nous permettra d'appeler ses fonctions en combinant l'interface IERC721 et l'adresse du contrat NFT.
In `nftId` (line 25), we store the specific token id in our NFT contract that will be auctioned.

Ensuite, nous avons besoin d'une variable pour stocker l'adresse de la personne qui met aux enchères le TVN, le « vendeur » (ligne 27).
Nous voulons que notre contrat NFT envoie au vendeur le produit de la vente aux enchères une fois terminée, c'est pourquoi utilisez `adresse payable`.

We create a state variable `endAt` (line 28) where we will store the end date of the auction.
We also create the two booleans, `started` (line 29) and `ended` (line 30), that keep track of whether the auction has started or ended.

Nous créons une variable `highestBidder` (ligne 32) où nous stockerons l'adresse de l'enchérisseur le plus élevé. We will send the highest bidder the NFT once the auction has ended.

Enfin, nous avons besoin d'un uint `highestBid` (ligne 33) pour stocker l'enchère la plus élevée et d'un mappage `bids` (ligne 34), où nous pouvons stocker la valeur totale des enchères qu'un compte a faites avant de retirer ; plus d'y d'autres choses dans la section suivante.

### Constructor

Lorsque le commissaire-priseur déploie le contrat, il doit fournir quelques arguments :L'adresse du contrat du TVN qu'ils veulent mettre aux enchères `_nft` (ligne 37), l'identifiant de jeton du NFT qu'ils veulent mettre aux enchères `_nftId` (ligne 38), et un prix de départ qui doit être surenchéri pour placer la première offre dans la vente aux enchères,`_startingBid` (ligne 39).

Once deployed, the state variables `nft` (line 41), `nftId` (line 42), `highestBid` (line 45) will be assigned the values from the arguments. The address of the `seller` that deployed the contract will be automatically read out via msg.sender and stored in the state variable `seller` (line 44).

In the next section, we will enable the auctioneer to start the auction and bidders to place their bids.

## ⭐️ Affectation

We will use the assignment part of the following sections to give you instructions on testing your contract in the Remix VM environment of Remix.

1. Déployer un contrat NFT. You can use the NFT contract that we created in our "3.3 ERC721 - Token Creation" section.

2. Deploy this EnglishAuction contract. Use the address of the NFT contract as an argument for the `_nft` parameter, 0 for `_nftId`, and 1 for `_startingBid`.

3. After deploying your contract, test if contract functions like `nft`, `nftId`, and `started` work as expected.