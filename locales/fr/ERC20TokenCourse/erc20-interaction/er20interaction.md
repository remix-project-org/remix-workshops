Dans cette section, nous allons déployer un contrat dans notre navigateur et tester sa fonctionnalité.

### 1. Déployer le contrat

**1.1** Compilez votre contrat EduCoin dans le module "Solidity compiler" de l'IDE Remix.

**1.2** In the "Deploy & run transactions" module, select your contract "EduCoin" in the contract input field and click on the "Deploy" button. Always make sure to select the correct contract in the contract selector input field.

**GIF** Compiler et déployer :
<0/>

### 2. Testez les fonctions

Expand the token contract functions in the IDE.

#### 2.1 Décimales

Click on the "decimals" button to call the decimals() function.
Il devrait retourner "18".

#### 2.2 Name

Click on the "name" button to call the name() function.
Il devrait renvoyer "EduCoin".

#### 2.3 Symbol

Click on the "symbol" button to call the symbol() function.
It should return "EDC".

#### 2.4 Total supply

Click on the "totalSupply" button to call the totalSupply() function.
Il devrait retourner 1000000000000000000000 (1000\*10\*\*18).

**GIF** Testez les décimales, le nom, le symbole et les fonctions de totalSupply :
<0/>

#### 2.5 Balance of

**2.5.1** Go to the "ACCOUNT" section in the sidebar and copy the displayed address by using the copy icon next to it.

**2.5.2** Paste the address in the input field next to the "balanceOf" function button and click on the button.
Il devrait retourner 1000000000000000000000 (1000\*10\*\*18).

**GIF** Test de l'équilibre de la fonction :
<0/>

#### 2.6 Transfer

We will transfer EduCoin from one account to a second account.

**2.6.1** Allez dans la section "COMPTE" dans la barre latérale et cliquez sur l'adresse affichée. This should open a dropdown. Sélectionnez la deuxième adresse affichée et copiez son adresse (compte 2).

**2.6.2** Open the dropdown and select the first account again (account 1), because this is the account that we want to use to make the transfer.

**2.6.3** Collez l'adresse dans le champ de saisie à côté du bouton de fonction "transfert", entrez le numéro 500000000000000000000 et cliquez sur le bouton.

**2.6.4** If you check the balances for account 1 and account 2, they should both return the amount 500000000000000000000.

**GIF** Fonction de transfert de test :
<0/>

#### 2.7 Approve

We will now allow account 1 to spend tokens on behalf of account 2.

**2.7.1** Allez dans la section "Compte", copiez l'adresse du compte 1, puis définissez-la à nouveau sur le compte 2.

**2.7.2** In the approve function, enter the address of account 1 as the input for spender and set the amount to 250000000000000000000.

**GIF** Fonction d'approbation de test :
<0/>

#### 2.8 Allocation

À côté du bouton "allocation", entrez l'adresse du compte 2 en tant que propriétaire et du compte 1 en tant que dépensier ; cliquez sur le bouton.
It should return 1000000000000000000000.

**GIF** Fonction d'allocation de test :
<0/>

#### 2.9 TransferFrom

Maintenant, le compte 1 transférera 2500000000000000000 de jetons du compte 2 vers son propre compte.

**2.9.1** Select account 1 in the "ACCOUNT" section.

**2.9.2** À côté du bouton "transferFrom", entrez l'adresse du compte 2 comme expéditeur et du compte 1 comme destinataire, entrez 25000000000000000000 comme montant et cliquez sur le bouton.

**2.9.3** Vérifiez les soldes des comptes 2 et 1, ils devraient retourner 2500000000000000000 et 7500000000000000000.

**GIF** Test transferFrom function:
<0/>