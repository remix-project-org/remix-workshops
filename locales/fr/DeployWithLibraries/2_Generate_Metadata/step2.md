## Déployer Bibliothèque

La bibliothèque du chapitre précédent était dans le même fichier que le contrat. Cependant, ils ne seront pas déployés ensemble et auront des adresses différentes.

Pour utiliser une bibliothèque, le contrat appelant doit avoir l'adresse de la bibliothèque.

Mais l'adresse de la bibliothèque n'est pas directement spécifiée dans le code Solidity. Le bytecode compilé du contrat appelant contient un espace réservé où les adresses de la bibliothèque seront insérées.

Lors du déploiement du contrat appelant, Remix recherchera l'adresse de la bibliothèque dans les métadonnées du contrat et mettra à jour l'espace réservé avec cette adresse.

Avant de déployer un contrat qui appelle une bibliothèque, vous devez générer les métadonnées du contrat (également appelées artefact de construction) et ensuite insérer l'adresse de la bibliothèque dans le fichier de métadonnées.

Les métadonnées d'un contrat sont générées au moment de la compilation.

Configurons Remix pour générer le fichier de métadonnées.

 - Allez dans le module des paramètres en cliquant sur l'icône des paramètres [paramètres](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/settings.png "Settings").

![module des paramètres](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_settings.png "Settings Module")

 - Et cochez la première option Générer les métadonnées du contrat.

# Compilez et générez le fichier de métadonnées (JSON).

1. Ouvrez le Compilateur Solidity ![Compilateur Solidity](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_icon_solidity.png "Solidity Compiler")

2. Compilez 2_contractSimpleLibrary.sol.

3. Passez à l'Explorateur de fichiers ![Explorateur de fichiers](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_file_explorer.png "File Explorer")

4. Naviguez vers les fichiers JSON nouvellement créés.
    - Ils devraient se trouver dans le dossier :

**browser/.learneth/DeployWithLibraries/2_Generate_Metadata/artifacts/**

5. Sélectionnez le fichier JSON nouvellement créé à partir du contrat.  Il porte le même nom que le contrat sample mais avec l'extension json : sample.json (ne sélectionnez pas les métadonnées de la bibliothèque contractSimpleLibrary.json).

Dans l'étape suivante, nous apporterons quelques ajustements au fichier de métadonnées.
