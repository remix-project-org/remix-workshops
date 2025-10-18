_Ether_ (ETH) est une crypto-monnaie. _Ether_ is also used to pay fees for using the Ethereum network, like making transactions in the form of sending _Ether_ to an address or interacting with an Ethereum application.

### Ether Units

To specify a unit of _Ether_, we can add the suffixes `wei`, `gwei`, or `ether` to a literal number.

#### `wei`

_Wei_ is the smallest subunit of _Ether_, named after the cryptographer [Wei Dai](https://en.wikipedia.org/wiki/Wei_Dai). _Ether_ numbers without a suffix are treated as `wei` (line 7).

#### `gwei`

One `gwei` (giga-wei) is equal to 1,000,000,000 (10^9) `wei`.

#### `ether`

One `ether` is equal to 1,000,000,000,000,000,000 (10^18) `wei` (line 11).

<0>Regardez un tutoriel vidéo sur Ether et Wei</0>.

## ⭐️ Assignment

1. Create a `public` `uint` called `oneGWei` and set it to 1 `gwei`.
2. Créez un `public` `bool` appelé `isOneGWei` et définissez-le sur le résultat d'une opération de comparaison entre 1 gwei et 10^9.

Tip: Look at how this is written for `gwei` and `ether` in the contract.