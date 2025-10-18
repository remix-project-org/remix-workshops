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

Di function `safeTransferFrom` (line 55) di transfer di ownership of a token with the id `tokenId` from di akant wit di address `from` go the account wit di address `to`.

Di function `safeTransferFrom` (line 137) dey almost same wit di function `safeTransferFrom` (line 55) . Di onli difference na dis func`safeTransferFrom` (line 55) . De only difference be say dis function get non-empty payload data.

Contract wey make sense must implement de ERC721TokenReciever Interface na to confirm transfer. Dis go ensure dat de contract fit handle ERC721 token transfer and go prevent de tokens from being locked to contract wey no fit.

### de transfer from

De function transferFrom (line 55) tranfer de ownership of token wey get de id tokenld from de account wey get de address from to de account wit de adress to.

**E go dey best if u use safeTransferFrom instead of transferFrom whenever e dey possible** The `transferFrom` function no dey secure because e no dey check if the smart contract wey the recipient of the transfer don implement the ERC721 TokenReceiver interface and if e fit handle ERC721 tokens.

## Advanced IERC721 Functions

### approve

Di function dey approve (line 94) dey give di akant wit di address to di permission to fit manage di token wit di I'd tokenld on behalf of di akant wey dey call di function.

### getApproved

Di fuktion `getApproved` (line 103) follow am back di address of di account (return var `operator`) wey dey give access to manage di tokin with di id `tokenId`.

### setApprovalForAll

Di function `setApprovalForAll` (line 115) dey set di permission (`_approved`) for di akant wit di specified addresss (input param - `operator`) to fit manage all Di token of di akant wey dey call di function.

### edeyApprovedForAll

Di function getApproved (line 103) go back di boolean true if di account wit di address operator dey approved to fit manage all tokens of di account wit di address owner.

## IERC721 Events

ERC721 contracts must to emit di following events:

### Transfer

Di Transfer event (line 15) gaz dey emitted wen di token wit di id tokenId dey transferred from di account wit di address from go di account wit di address to.

### Accept am

The `Approval` event (line 20) gats dey emitted when the account wey get the address `owner` approves the account wey get the address `spender` to manage the token with the id `tokenId` on him behalf.

### Approval for everybody

Di ApprovalForAll event (line 25) gaz dey emitted wen di account wit di address owner dey give or commot di permission (_approved) of di account wit di address operator for management of all its tokens.

## IERC165

For addition to di ERC721 interface ERC721 compliant contracts gaz dey implement di ERC165 interface.

For di implementation of di ERC165 intaface contrakts fit declare di support of specific intaface. Contract wey wan relate wit another contract fit come query if di other contract dey support dis interface before e maketransaction like to send tokens to am wey dem fit no support.

Our IERC721intaface here dey bring (line 6) make e inherit (line 11) from di IERC165 intaface.

Na like dis <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/introspection/IERC165.sol" target="_blank">OpenZEppelins implementation </a> of di ERC165 intaface be like:

```
interface IERC165 {
function dey supportsInterface(bytes4 interfaceId) external view go back (bool);
}
```

Like now, di ERC165 indentifier for di ERC721 intaface as dem specify am for di EIP721 na “0x80ac58cd”. Sabi how to calculate an interface identifier and more about the ERC165 in its <a href="https://eips.ethereum.org/EIPS/eip-165" target="_blank">improvement proposal</a>.

## Oda intaface

Di <a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">IERC721TokenReceiver</a> intaface must dey implemented to fit accept safe transfer.

E get two optional extensions for ERC721 contract wey dem specify for di EIP721:

IERC721 Enumerable dey gree make contract publish im full list of token and make pipu fit see am.

IERC721 Metadata dey gree make contrakt fit associate info to add join to token. We go get more deep look into am for di next place.
