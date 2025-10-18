In this contract, we use an ERC721 token contract implementation from OpenZeppelin (line 4).

Jetez un coup d'œil à leur mise en œuvre d'un <0>contrat ERC721</0>. Apart from the functionality specified in the ERC721 standard, the contract provides additional functions which we will see in a bit.

## myToken

Nous créons notre propre contrat appelé MyToken (ligne 7), qui hérite (ligne 7) de la fonctionnalité de l'implémentation du contrat de jeton OpenZepplin `ERC721` et de `Ownable` que nous avons importé (ligne 4). If you don't remember the Ownable contract module, have a look at the ERC20 extensions section.

This ERC721 implementation makes use of the IERC721Metadata extension that is specified in the EIP. Notre contrat hérite des fonctions `name()` et `symbol()`
et dispose d'un constructeur qui permet de définir leurs valeurs pendant le déploiement du contrat (ligne 8).
In this case, we are going to use the default values. We name our token the same as the contract `"MyToken"` and make `"MTK"` its symbol.

### Base URI

With an ERC721 contract, we are able to mint various tokens, each with its own tokenId. As we saw in the IERC721Metadata interface, each token can have its own `tokenURI`, which typically points to a JSON file to store metadata like name, description, and image link.
If a contract mints multiple tokens, ERC721 implementations often use the same URI as a base (`baseURI`) for all tokens and only differentiate them by adding their unique `tokenId` at the end via concatenation. In the next part, we will see what this looks like in practice.

In this example, we are storing our data on IPFS — more on that in the next section. Notre URI de base est <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/</a> (ligne 11).
Par concaténation, le tokenURI pour le jeton avec l'identifiant 0 serait <0>https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0</0> , le tokenURI pour le jeton avec l'identifiant 1 serait <1>https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1</1>, et ainsi de suite.

When using IPFS and you run into "504 Gateway Time-out" errors, you might have to wait and retry until the data is available.

### safeMint

With the safeMint function (line 14) we enable the owner to create new tokens with a dedicated token id after contract deployment.
La fonction safeMint fait partie de l'implémentation ERC721 d'OpenZeppelin et nous permet de frapper en toute sécurité un jeton avec l'identifiant `tokenId` sur le compte avec l'adresse `to`. For access control, we use the `onlyOwner` modifier from the Ownable access control contract module that we imported (line 5).

In the next section, we will see how we can create and host the metadata for our NFTs.

## ⭐️ Assignment

1. Rename your contract to `Geometry`.
2. Rename your token to `Geometry`.
3. Change the symbol of your token to `GEO`.
4. Changez le `_baseURI` en <0>https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/</0>.
