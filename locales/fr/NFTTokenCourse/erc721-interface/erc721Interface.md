ERC721 is a standard for token contracts that manage non-fungible tokens (NFTs) on the Ethereum blockchain.

Each non-fungible token is unique and not interchangeable. NFTs can have different properties, behavior, or rights. Non-fungible tokens are used to represent ownership of unique digital and physical assets like art, collectibles, or real estate.

Si vous voulez en savoir plus sur la norme de jeton ERC721, jetez un coup d'œil aux spécifications de sa <0>proposition d'amélioration Ethereum</0>.

## Interface

The ERC721 standard is more complex than the ERC20 standard and it features optional extensions. ERC721 compliant contracts must, at a minimum, implement the ERC721 and ERC165 interfaces, which we will look at in this section.

Cette interface (ligne 11) fait partie de la bibliothèque de contrats open source fournie par <0>OpenZeppelin</0>.

## Basic IERC721 Functions

Contracts compliant with the ERC721 standard have to implement the following functions:

### balanceOf

The function `balanceOf` (line 30) returns the amount of tokens owned by the account with the address `owner`.

### ownerOf

The function `ownerOf` (line 39) returns the address `owner` of the account that holds the token with the id `tokenId`.

### safeTransferFrom

The function `safeTransferFrom` (line 55) transfers the ownership of a token with the id `tokenId` from the account with the address `from` to the account with the address `to`.

The function `safeTransferFrom` (line 137) is almost identical to the function `safeTransferFrom` (line 55) .The only difference is that this function has a non-empty payload `data`.

Un contrat intelligent doit mettre en œuvre l'interface ERC721TokenReceiver s'il doit recevoir un transfert. Cela garantira que le contrat peut gérer les transferts de jetons ERC721 et empêcher les jetons d'être verrouillés dans un contrat qui ne le peut pas.

### transferFrom

The function `transferFrom` (line 55) transfers the ownership of a token with the id `tokenId` from the account with the address `from` to the account with the address `to`.

**It is recommended to use safeTransferFrom instead of transferFrom whenever possible.**
The `transferFrom` function is not secure because it doesn’t check if the smart contract that is the recipient of the transfer has implemented the ERC721TokenReceiver interface and is capable of handling ERC721 tokens.

## Advanced IERC721 Functions

### approve

La fonction `approve` (ligne 94) donne au compte avec l'adresse `to` la permission de gérer le jeton avec l'identifiant `tokenId` au nom du compte appelant la fonction.

### getApproved

The function `getApproved` (line 103) returns the address of the account (return var `operator`) that is approved to manage the token with the id `tokenId`.

### setApprovalForAll

The function `setApprovalForAll` (line 115) sets the permission (`_approved`) for the account with the specified address (input param - `operator`) to manage all tokens of the account calling the function.

### isApprovedForAll

The function `getApproved` (line 103) returns the boolean true if the account with the address `operator` is approved to manage all tokens of the account with the address `owner`.

## IERC721 Events

Les contrats ERC721 doivent également émettre les événements suivants :

### Transfer

The `Transfer` event (line 15) must be emitted when the token with the id `tokenId` is transferred from the account with the address `from` to the account with the address  `to`.

### Approval

The `Approval` event (line 20) must be emitted when the account with the address `owner` approves the account with the address `spender` to manage the token with the id `tokenId` on its behalf.

### ApprovalForAll

The `ApprovalForAll` event (line 25) must be emitted when the account with the address `owner` gives or removes the permission (`_approved`) of the account with the address `operator` to manage all its tokens.

## IERC165

In addition to the ERC721 interface, ERC721 compliant contracts must also implement the ERC165 interface.

With the implementation of the ERC165 interface, contracts can declare the support of specific interfaces. A contract that wants to interact with another contract can then query if the other contract supports this interface before making a transaction e.g. sending tokens to it that they might not support.

Our IERC721 interface here imports (line 6) and inherits (line 11) from the IERC165 interface.

Voici à quoi ressemble <0>l'implémentation OpenZeppelins</0> de l'interface ERC165 :

```
interface IERC165 {
    function supportsInterface(bytes4 interfaceId) external view returns (bool);
}
```

Par exemple, l'identifiant ERC165 pour l'interface ERC721 comme spécifié dans l'EIP721 est "0x80ac58cd". Apprenez à calculer un identifiant d'interface et en savoir plus sur l'ERC165 dans sa <0>proposition d'amélioration</0>.

## Other interfaces

L'interface <0>IERC721TokenReceiver</0> doit être implémentée pour accepter les transferts sécurisés.

Il existe deux extensions facultatives pour les contrats ERC721 spécifiées dans l'EIP721 :

IERC721Enumerable enables a contract to publish its full list of tokens and make them discoverable.

IERC721Metadata enables a contract to associate additional information to a token. We will have a more detailed look into this in the next section.
