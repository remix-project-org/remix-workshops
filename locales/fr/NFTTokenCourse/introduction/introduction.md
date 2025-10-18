In this section of the course, we will give you a theoretical introduction to blockchain-based tokens.

Les jetons Blockchain sont un nouveau bloc de construction technologique créé par la technologie blockchain (comme les sites Web l'étaient pour Internet) qui permet un Internet décentralisé et propriétaire (web3).

### Introduction

In the context of web3, tokens represent ownership. Tokens can represent ownership of anything: art, reputation, items in a video game, shares in a company, voting rights, or currencies.

The revolutionary innovation of blockchain technology is that it allows data to be stored publicly in an immutable (unchangeable) way.
This new form of data storage allows us to keep track of ownership and enable truly ownable digital items for the first time.

Blockchain Technology was originally invented to keep track of the ownership of Bitcoin, a decentralized digital currency and fungible token.

### Fungible and non-fungible tokens

Des actifs comme l'argent : Bitcoin ou un billet d'un dollar, par exemple, sont fongibles. Fungible means that all assets are the same and are interchangeable. Assets like art, collectibles, or houses are non-fungible; they are all different and not interchangeable.

We can divide tokens into these two types: fungible tokens, where all tokens are the same, and non-fungible tokens (NFTs), where every token is unique.

### Norme de jeton

The behavior of a token is specified in its smart contract (token contract). The contract could, for example, include the functionality to transfer a token or check for its total supply.

If everybody would create their own token contracts with different behavior and naming conventions, it would make it very hard for people to build contracts or applications that are able to interact with each other.

La communauté Ethereum a développé des normes de jetons qui définissent comment un développeur peut créer des jetons interopérables (capables de travailler avec d'autres) avec d'autres contrats, produits et services. Contracts developed under these standards need to include a certain set of functions and events.

The most popular token standards are the ERC20 for fungible tokens and the ERC721 for non-fungible tokens. In this course, we will learn how to create and interact with NFTs, tokens created with the ERC721 token standard.

If you want to learn more about fungible tokens and the ERC20 token standard, have a look at the Learneth ERC20 Token Course.

The ERC777 is a fungible token standard, like the ERC20, that includes more advanced features like hooks while remaining backward compatible with ERC20. En savoir plus sur l'ERC777 dans sa <0>EIP (proposition d'amélioration de l'Ethereum)</0>.

The ERC1155 is a multi-token standard that allows a single contract to manage different types of tokens, such as fungible, non-fungible, or semi-fungible tokens.
En savoir plus sur l'ERC1155 dans son <0>EIP</0>.

## ⭐️ Affectation

For this assignment, we will test your knowledge via a short quiz.
Assign the number of the best answer to the variables `question1` (line 5),
`question2` (line 6), `question3` (line 7) in the `Quiz` contract (line 4).

### Question 1:

Pourquoi les jetons basés sur la blockchain sont-ils si révolutionnaires ?

1. Because people can now make investments anonymously.
2. Because they represent ownership in digital assets that can be owned and transferred.
3. Because you can use tokens to make transactions without having to pay taxes.

### Question 2:

Pourquoi la communauté a-t-elle créé des normes de jetons ?

1. So that the community can control and approve the tokens that are created.
2. In order to restrict the functionality of tokens to safe and non-malicious actions.
3. So that the community can create tokens that are interoperable with other contracts, products, and services.

### Question 3:

If you would create a decentralised application for a baseball trading card game where each baseball player would be represented by a token, what token standard would you use to write the token contract?

1. ERC20
2. ERC721