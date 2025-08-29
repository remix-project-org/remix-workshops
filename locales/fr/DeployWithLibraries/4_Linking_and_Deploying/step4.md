Passez au module Déployer & Exécuter.
![Run transaction](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/remix_runtransaction.png "Run Transaction")

- Sélectionnez l'Environnement VM Remix et sélectionnez le contrat sampleContract dans la liste des contrats compilés.

- Cliquez sur Déployer

Le terminal devrait afficher quelque chose comme `création de sample errored : <address> n'est pas une adresse valide. Veuillez vérifier que l'adresse fournie est valide. C'est attendu : **Nous avons définiautoDeployLibà faux, donc Remix s'attend à avoir une adresse et pas seulement<address>`\*\*

Nous devons donc déployer la bibliothèque pour obtenir son adresse.

- Sélectionnez la bibliothèque aLib dans la liste des contrats compilés et cliquez sur déployer

  ![Choose aLib](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/contract_alib.png "Choose aLib")

- Cliquez sur l'icône du presse-papiers pour copier l'adresse de la bibliothèque.

  ![Copy lib1](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/alib_copy.png "Copy")

- Paste it into the **contract sample's** metadata JSON.

- Reselect the `sampleContract` contract in the `Run transaction` module and hit deploy.

- Le déploiement devrait maintenant réussir.

