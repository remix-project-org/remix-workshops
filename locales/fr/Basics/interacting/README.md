## Accéder aux fonctions d'un contrat déployé

1. Lorsqu'un contrat a été déployé avec succès, il apparaîtra en bas du plugin Déployer et Exécuter. Ouvrez le contrat en cliquant sur le caret - de sorte que le caret pointe vers le bas.
   ![contrat déployé](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/instance.png "deployed contract")

2. Il y a 2 fonctions dans ce contrat.  Pour saisir les paramètres individuellement, cliquez sur le caret à droite de changeOwner (entouré en rouge ci-dessous). Dans la vue étendue, chaque paramètre a sa propre boîte de saisie.

![contrat déployé](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/deployed_open2.png "deployed contract")

Si ce contrat avait importé d'autres contrats, les fonctions des contrats importés seraient également visibles ici.  À un moment donné, essayez de jouer avec un contrat ERC20 pour voir toutes ses nombreuses fonctions.

3. Les fonctions avec des boutons bleus sont soit des fonctions pures, soit des fonctions view.  Cela signifie qu'elles ne font que lire une propriété ou retourner une valeur.  En d'autres termes, elles n'enregistrent rien - donc elles sont GRATUITES (elles ne coûtent pas de gaz).  Les fonctions avec d'autres couleurs - généralement orange (selon le thème Remix) coûtent du gaz car elles enregistrent des informations.  Elles créent une transaction.

4. 2_Owner.sol n'a pas de fonction payable.  Si c'était le cas, la couleur du bouton serait rouge.  Les fonctions payables vous permettent d'envoyer de l'Ether à la fonction.  Pour envoyer de l'ETH avec une fonction payable, vous indiquez le montant que vous souhaitez envoyer dans le champ valeur vers le haut du module Déployer & Exécuter.

5. Dans la VM Remix, vous n'avez pas besoin d'approuver une transaction.  Lorsque vous utilisez un environnement de test plus réaliste ou le réseau principal, vous devrez approuver les transactions pour qu'elles soient effectuées. Approuver une transaction coûte du gaz.

6. Le choix d'un réseau public ne se fait pas dans Remix, mais dans votre portefeuille de navigateur.  Il y a une icône de prise à droite du titre Environnement qui mène à chainlist.org où vous pouvez obtenir les spécifications de la chaîne avec laquelle vous souhaitez interagir.
   ![chainlist](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/chainlist.png "chainlist")
