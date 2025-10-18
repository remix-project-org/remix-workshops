ERC20 (Ethereum Request for Comments 20) na standard for token contracts ey dey manage fungible tokens for di Ethereum blockchain.

Fungible token dem all dey equal to each oda and dem get di same, value, behaviour and right. Dem dey quick use fungible token as wetin dem take dey exchange like dem foreign money ETH or BTC. Well sha, dem fit get oda use cases like to dey vote right or reputation.

If you wan know more inside di ERC20 token standard you go go look di specs for <a href="https://eips.ethereum.org/EIPS/eip-20" target="_blank">Ethereum improvement proposal</a>.

## Di interface

To fit get di whole view of di function wey e need for ERC20 oken contract, we go look di interface wey dey follow ERC20 contract.
Di intaface (line 9) na part of di open source contract library wey be say na <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.4.0/contracts/token/ERC20/IERC20.sol" target="_blank">OpenZeppelin</a> bring am.

## ERC20 Im Functions

Contracts compliant wit di ERC20 standard must to implement di following six function:

### ditotalSupply

Di function `totalSupply` (line 13) dey return di total amount of tokens wey dey available.

### balanceOf

Di function `balanceOf` (line 18) dey return di amount of tokens wey dey owned by di account wit di address `account`.

### send am

Di function `transfer` (line 27) transfers `amount` of tokens to di address `recipient`.
Dis function **must** to emit (produce) a `Transfer` event (look am down) and **should** throw exception when di sender no get enough tokens to fit make di transfer.

### gree for am

Di function `approve` (line 52) dey create allowance for the address `spender` to fit make transfer `amount` of token on behalf of di account wey dey call di function.

### allowee

Di function `allowance` (line 36) dey return di amount of token wey di address `spender` dey allowed to spend on behalf of di account wit di address owner.

### di transferFrom

Di function `transferFrom` (line 63) transfers `amount` of tokens on behalf of di address `sender` go di address recipient.
Dis fuction **must** showcase `Transfer` event.

## ERC20 Im Events

ERC20 contracts must to emit two events sha:

### Carry am go

Di `Transfer` (line 71) event must to dey emitted when `value` amount of tokens dey transferred from di account wit di address `indexed from` to `indexed to`. Di parameters `from` and `to` dey \`indexed e dey gree make we search dis events come dey use di indexed paameters as filters.

### E accept am

Di  `Approval` (line 77)  event must dey emitted wen the account `indexed owner` approve di account `indexed spender` to take transfer `value` amount of tokens on im behalf.

## ERC20 functions wey no need

To add join di amndatory function wit event e get thre function wey no need wey dem specift for ERC20 wey dem no implement for dis intaface:

### wetin dem dey call am

`function name() external view wey dey return (string);`

Send di name of di token back.

### sign

`function symbol() external view wey dem return (string);`

Send di sign of di token back.

### decimals

\`function decimals() external view wey dem return (uint8)

Send bak di number of decimal place wey di token use.

You fit wan use decimal to fit take divide your toke into small amountlike 1.5 ETH wen den show am. Di EVM (Ethereum virtual machine) only dey supports integer numbers. Na why di ERC20 standard want make e suggest di decimal function wey dey specify how many decimal di token get. 18 decimal place na di industry standard.
