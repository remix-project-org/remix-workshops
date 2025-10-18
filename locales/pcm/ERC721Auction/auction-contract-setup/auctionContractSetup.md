For dis contract tutorial we learn how to fit create ERC721 auction contract.
We fit recommend u to fit learneth"Solidity NFT Course" before starting this tutorial.

Di ff area we fit create contract wey fit enable seller auction an NFT to di highest bidder. Dis contract dey created by di <a href="https://solidity-by-example.org/app/english-auction/" target="_blank">Solidity by Example</a> project. For dis section we fit create an interface wey dey neccessary state variables, and di constructor.

### Di interface

We fit create di interface (line 5) for the ERC721 token since our contract will need to interact with am. We go need di safeTransferFrom` (line 5),  and` transferFrom\` (line 11) methods.

### Di EnglishAuction

We go create four events`Start`, `Bid`, `Withdraw`, `End` (line 19-22) so we can log important interactions.

We must create di state variablea wey store all di necessary information about our auction on-chain.

We fit create two state variables for the NFT we want to auction. Di variable nft`(line 24) we go store representative of di NFT contract, wey go allow us to call its functions by combining the interface IERC721 and di address of the NFT contract.
In`nftId\` (line 25), we fit store di specific token id in our NFT contract that will be auctioned.

Next we fit variable to fit store di address fo di person wey dey auction di NFT, di seller (line 27).
Functionality dey from ERC20 and we don override dis function, other contracts fit inherit from us and override dis function too.

"We create one state variable endAt (line 28) wey go store di auction end date."
We still create two booleans, started (line 29) and ended (line 30), wey dey track whether auction don start or don end.".

We fit create variable `highestBidder` (line 32) where we will store the address of the highest bidder. We fit send di hidhest bidder di NFT once d auction don end.

E do reach uint `highestBid` (line 33) to store de highest bid and a mapping `bids` (line 34), where we fit store de total value of bids dat an account has made before withdrawing; more on this in the next section.

### Di Constructor

When auctioner deploy contract dem go need provide few argument: di address of di contract of di NFT dem go wan auction nft`(line 37), de token id of de NFT they want to auction`_nftId` (line 38), and a starting price that must be overbid to place the first bid in the auction,`_startingBid\` (line 39).

Once deploydi state variables `nft` (line 41), `nftId` (line 42), `highestBid` (line 45) dem go assigned de values from de arguments. Di address of di seller wey deployed di contract go be automatically read am out.

For dis area we fit enable di auctioneer start di auction and bidders to fit place their bids.

## di ⭐️ Assignment

We fit use assignment part of di ff sections to fit give u instructions on testing ur contract in di remix VM environment of remix.

1. U go deploy NFT contract. U fit use di NFT contract wey we create for our "3.3 ERC721 - Token Creation" section.

2. Use dis EnglishAuction contract. Use di NFT contract im address take argue di `_nft` parameter, 0 for `_nftId`, and 1 for `_startingBid`.

3. When u don deploy ur contract test if contrat functions like`nft`, `nftId`, and `started` work as expected.