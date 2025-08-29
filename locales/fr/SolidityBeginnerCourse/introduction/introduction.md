Welcome to this interactive Solidity course for beginners.

In this first section, we will give you a short preview of the concepts we will cover in this course, look at an example smart contract, and show you how you can interact with this contract in the Remix IDE.

Ce contrat est un contrat de comptoir qui a la fonctionnalité d'augmenter, de diminuer et de retourner l'état d'une variable de compteur.

If we look at the top of the contract, we can see some information about the contract like the license (line 1), the Solidity version (line 2), as well as the keyword `contract` and it's name, `Counter` (line 4). We will cover these concepts in the next section about the **Basic Syntax**.

Avec `uint public count` (ligne 5), nous déclarons une variable d'état de type `uint` avec la visibilité `public`. We will cover these concepts in our sections about **Variables**, **Primitive Data Types**, and **Visibility**.

We then create a `get` function (line 8) that is defined with the `view` keyword and returns a `uint` type. Specifically, it returns the `count` variable. This contract has two more functions, an `inc` (line 13) and `dec` (line 18) function that increases or decreases our count variable.
We will talk about these concepts in our sections about **Functions - Reading and Writing to a State Variable** and **Functions - View and pure**.

## Compile and Deploy through Remix

**GIF** Interaction avec le contrat :
<0/>

1. Nous pouvons compiler votre contrat `Counter` dans le module "Solidity compiler" de l'IDE Remix.

2. Dans le module "Déployer et exécuter les transactions", nous sélectionnons notre contrat "Compteur" dans le champ de saisie du contrat et cliquons sur le bouton "Déployer".

3. We expand the token contract functions in the IDE, and test its `get`, `inc`, and `dec` functions.

## ⭐️ Affectation

Throughout this course, we will give you assignments to test and consolidate your newly acquired knowledge.

Your first assignment is to:

1. Compilez ce contrat.
2. Deploy it to the Remix VM.
3. Interact with your contract.
