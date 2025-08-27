ERC721 na di standard for token kontract wey dey manage non fungible token (NFTs) for di ethereum blokchain.

Everi token wey no dey fungible dey sweet and u no fit change am. NFTs fit get different propati, behaviour or rights. Token wey no dey fungible dem dey use am represent d owner of assets wey unique and dem dey digital and one on one dem arts, collectible or land.

If you wan sabi plenti on top di ERC721 token standard you go look di specs for im <a href="https://eips.ethereum.org/EIPS/eip-721" target="_blank">Ethereum improvementof im proposal</a>.

## Di intaface

Di aerc271 dey hard pass di ERC20 standad wit im feature extension wey be less opshion. ERC721 compliant contracts must, to from small dey implement di ERC721 an di ERC165 intaface, wey we go check for dis place.

Dis intaface (line 11) na part of di open source contrakt library wey <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/IERC721.sol" target="_blank">OpenZeppelin</a> bring.

## Di basic IERC721 im function

Contraks wey compli wit di ERC721 standard go need impliment dis functions dem:

### di balance na

Di function wey dem dey call `balanceOf` (line 30) dey return di amount of tokens wey who get di account wit di address `owner`.

### ownaOf

Di function `ownerOf` (line 39) dey return di address `owner` of di account wey dey hold di token wit de id `tokenId`.

### safeTransferFrom

The function `safeTransferFrom` (line 55) transfers the ownership of a token with the id `tokenId` from the account with the address `from` to the account with the address `to`.

The function `safeTransferFrom` (line 137) is almost identical to the function `safeTransferFrom` (line 55) .The only difference is that this function has a non-empty payload `data`.

A smart contract must implement the ERC721TokenReceiver Interface if it is to receive a transfer. This will ensure that the contract can handle ERC721 token transfers and prevent the tokens from being locked in a contract that can’t.

### transferFrom

The function `transferFrom` (line 55) transfers the ownership of a token with the id `tokenId` from the account with the address `from` to the account with the address `to`.

**It is recommended to use safeTransferFrom instead of transferFrom whenever possible.**
The `transferFrom` function is not secure because it doesn’t check if the smart contract that is the recipient of the transfer has implemented the ERC721TokenReceiver interface and is capable of handling ERC721 tokens.

## Advanced IERC721 Functions

### approve

The function `approve` (line 94) gives the account with the address `to` the permission to manage the token with the id `tokenId` on behalf of the account calling the function.

### getApproved

The function `getApproved` (line 103) returns the address of the account (return var `operator`) that is approved to manage the token with the id `tokenId`.

### setApprovalForAll

The function `setApprovalForAll` (line 115) sets the permission (`_approved`) for the account with the specified address (input param - `operator`) to manage all tokens of the account calling the function.

### isApprovedForAll

The function `getApproved` (line 103) returns the boolean true if the account with the address `operator` is approved to manage all tokens of the account with the address `owner`.

## IERC721 Events

ERC721 contracts must also emit the following events:

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

This is how <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/introspection/IERC165.sol" target="_blank">OpenZeppelins implementation</a> of the ERC165 interface looks like:

```
interface IERC165 {
    function supportsInterface(bytes4 interfaceId) external view returns (bool);
}
```

For example, the ERC165 identifier for the ERC721 interface as specified in the EIP721 is “0x80ac58cd”. Learn how to calculate an interface identifier and more about the ERC165 in its <a href="https://eips.ethereum.org/EIPS/eip-165" target="_blank">improvement proposal</a>.

## Other interfaces

The <a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">IERC721TokenReceiver</a> interface must be implemented to accept safe transfers.

There are two optional extensions for ERC721 contracts specified in the EIP721:

IERC721Enumerable enables a contract to publish its full list of tokens and make them discoverable.

IERC721Metadata enables a contract to associate additional information to a token. We will have a more detailed look into this in the next section.
