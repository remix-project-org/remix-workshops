For dis contract we go use ERC20 token contract implementation from openzepplin (line 4).

U go look dier implementation of a<a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/ERC721.sol" target="_blank">ERC721 contract</a>. Apart from di functionality specified in di ERC20 standard dis contract provides additional functionality.

## my Token

We fit still create our own contract called MY TOKEN (line 6), which inherits the functionality from the OpenZepplin ERC20 token contract implementation that we imported (line 4). If u no remember the ownable contract module just go look the ERC20 extensions section.

This ERC721 implementation makes use of the IERC721Metadata extension that is specified in the EIP. Our contract dey inherits di functions name() wit symbol() and e get constructor wey dey allow dem values to dey set during di deployment of di contract (line 8).
For this situation we go gat use the default values. We fit call our token di same as di contract `"MyToken"` and make `"MTK"` its symbol.

### Base URl

Wit ERC721 contrakt, we fit mind plenti kind token each one get im own tokenld. Like we don see for di IERC721Metadata interface, each token fit get im own tokenURI wey typically dey point to JSON file to store metadata like name description wit image link.
If contract dey mint multiple tokens ERC721 implementations dey often use di same URI as base (baseURI) for all tokens and only dey differentiate dem as e dey put their unique tokenId for di end via concatenation. For the next part we go see wetin this go look like for pratice.

For this example we dey store our data for IPFS _ plenty of am for the next session. Our baseURI na <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/</a> (line 11).
Through concatenation the tokenURI for the token with the id 0 go be <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0</a> , the tokenURI for the token with the id 1 go be <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1</a>, and so on.

When you dey use IPFS and you jam “504 Gateway Time-out” errors you go gats to wait den retry until di data dey available.

### safeMint

For di safeMint function (line 14) we make sure say di owner fit create new tokens wit dedicated token id after contract deployment.
Di safeMint function na part of di ERC721 implementation of OpenZeppelin and dem dey let us dey mint tokenwit no wahala wit di id tokenId for di account wit di address to. For access control we dey use the `onlyOwner` modifier wey dey the ownable access control contract module wey we import (line 5).

For the next section we go see how we go fit take create and host metadata for our NFTs.

## Home work

1. Rename your contract to `Geometry`.
2. Rename your token to `Geometry`.
3. Change the symbol of ur token to `GEO`.
4. Change the `_baseURI` to <a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/" target="_blank">https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/</a>.
