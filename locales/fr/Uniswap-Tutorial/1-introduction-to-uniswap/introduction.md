In this tutorial, we'll explore the Uniswap V3 Swap contract to learn about how single-hop and multi-hop swaps work.

But first, some Uniswap fundamentals.

## Qu'est-ce qu'Uniswap ?

Uniswap is a decentralized cryptocurrency exchange. It allows users to exchange tokens without the need for a centralized intermediary. Uniswap is a key player in the decentralized finance (DeFi) space.

## How does Uniswap work?

Au lieu d'utiliser un carnet de commandes comme un échange centralisé traditionnel, Uniswap utilise un modèle de teneur de marché automatisé (AMM). Dans Uniswap, l'AMM est un contrat intelligent qui détient des réserves de jetons (Liquidity Pool). Users can trade between tokens in the Liquidity Pool. The price of each token is determined by the ratio of the reserves.

### Step-by-step example of a Uniswap trade

1. Alice veut échanger 1 ETH contre DAI.
2. Alice sends 1 ETH to the Uniswap smart contract.
3. Le contrat intelligent Uniswap calcule le montant du DAI qu'Alice devrait recevoir en fonction du taux de change actuel.
4. The Uniswap smart contract sends the DAI to Alice.
5. The Uniswap smart contract adds the 1 ETH to its reserves.
6. The Uniswap smart contract recalculates the exchange rate based on the new reserves.

The tokens in the Liquidity Pool are provided by Liquidity Providers. Lorsqu'un fournisseur de liquidités dépose des jetons dans un pool de liquidités, il reçoit des jetons de fournisseur de liquidité en retour. Liquidity Provider Tokens represent a user's share of a Liquidity Pool.

Users of Uniswap pay a fee for each trade. Les frais sont payés aux fournisseurs de liquidités sous la forme de jetons de fournisseurs de liquidités supplémentaires.

## Uniswap Swap Contract

Le contrat Uniswap Swap permet aux utilisateurs d'échanger des jetons en utilisant Uniswap V3. It can do single-hop swaps, which allow users to exchange one token for another directly. Il peut également faire des échanges multi-sauts, ce qui signifie que les utilisateurs peuvent échanger un jeton contre un autre en acheminant plusieurs jetons. Routing in this context means that the swap contract will exchange the token for another token, then exchange that token for another token, and so on until it reaches the desired token.

## Conclusion

Dans cette section, nous avons découvert Uniswap, comment il fonctionne et comment nous allons l'utiliser pour échanger des jetons.

## ⭐️ Assignment: Multiple Choice Test

### 1. What is Uniswap?

1. A centralized exchange protocol.
2. A decentralized exchange protocol that uses an order book.
3. A decentralized exchange protocol that uses an automated market maker (AMM) model.
4. A decentralized exchange protocol that uses an order book and an automated market maker (AMM) model.

### 2) How does Uniswap determine the price of a token?

1. Le prix d'un jeton est déterminé par le ratio des réserves.
2. The price of a token is determined by the ratio of the reserves and the number of trades.
3. The price of a token is determined by the ratio of the reserves and the number of Liquidity Providers.