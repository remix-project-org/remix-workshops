ERC20 (Ethereum Request for Comments 20) is a standard for token contracts that manages fungible tokens on the Ethereum blockchain.

Fungible tokens are all equal to each other and have the same value, behavior, and rights. Les jetons fongibles sont souvent utilisés comme moyen d'échange, comme les devises ETH ou BTC. Cependant, ils peuvent également avoir d'autres cas d'utilisation comme le droit de vote ou la réputation.

Si vous voulez en savoir plus sur la norme de jetons ERC20, jetez un coup d'œil aux spécifications de sa <0>proposition d'amélioration Ethereum</0>.

## Interface

To get an overview of the required functionality of an ERC20 token contract, we will look at an interface that interacts with an ERC20 contract.
Cette interface (ligne 9) fait partie de la bibliothèque de contrats open source fournie par <0>OpenZeppelin</0>.

## ERC20 Functions

Contracts compliant with the ERC20 standard must implement the following six functions:

### totalSupply

La fonction `totalSupply` (ligne 13) renvoie le nombre total de jetons disponibles.

### balanceOf

La fonction `balanceOf` (ligne 18) renvoie la quantité de jetons appartenant au compte avec l'adresse `compte`.

### transfer

The function `transfer` (line 27) transfers `amount` of tokens to the address `recipient`.
This function **must** emit (produce) a `Transfer` event (see below) and **should** throw an exception when the sender doesn't have enough tokens to make the transfer.

### approve

The function `approve` (line 52) creates an allowance for the address `spender` to transfer `amount` of tokens on behalf of the account calling the function.

### allowance

La fonction `allowance` (ligne 36) renvoie le nombre de jetons que l'adresse `spender` est autorisé à dépenser au nom du compte avec l'adresse `propriétaire`.

### transferFrom

La fonction `transferFrom` (ligne 63) transfère `montant` de jetons au nom de l'adresse `expéditeur` à l'adresse `destinataire`.
This function **must** emit a `Transfer` event.

## ERC20 Events

ERC20 contracts must also emit two events:

### Transfer

The `Transfer` (line 71) event must be emitted when `value` amount of tokens are transferred from the account with the address `indexed from` to `indexed to`. The parameters `from` and `to` are `indexed` allowing us to search for these events using the indexed parameters as filters.

### Approval

The `Approval` (line 77)  event must be emitted when the account `indexed owner` approves the account `indexed spender` to transfer `value` amount of tokens on its behalf.

## ERC20 Fonctions optionnelles

In addition to the mandatory functions and events, there are also three optional functions specified in the ERC20 standard that are not implemented in this interface:

### name

`function name() vue externe renvoie (chaîne) ;`

Returns the name of the token.

### symbol

`function symbol() external view returns (string);`

Returns the symbol of the token.

### Décimales

`function decimals() external view returns (uint8);`

Returns the number of decimal places the token uses.

You may want to use decimals to make your token divisible into arbitrary amounts like 1.5 ETH when displayed. The EVM (Ethereum virtual machine) only supports integer numbers. That's why the ERC20 standard suggests to implement the decimal functionality that specifies how many decimal places a token has. 18 decimal places is the industry standard.
