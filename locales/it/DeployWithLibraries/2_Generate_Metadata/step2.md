## Deploying Library

La **library** del capitolo precedente era nello stesso file del **contract**. Tuttavia, non verranno deployati insieme e avranno indirizzi diversi.

Per poter usare una libreria, il contratto che la richiama deve avere l’**address** della libreria.

Ma l’indirizzo della libreria non è specificato direttamente nel codice Solidity. Il bytecode compilato del contratto che la richiama contiene un placeholder dove andranno gli address della libreria.

Al momento del deploy del **contratto chiamante**, Remix cercherà l’indirizzo della libreria nei **metadata** del contratto e aggiornerà il placeholder con l’indirizzo.

Quindi, prima di fare deploy di un contratto che richiama una libreria, devi generare i metadata del contratto (ossia il suo build artifact) e poi inserire l’indirizzo della libreria nel file dei metadata.

I metadata di un contratto vengono generati in **fase di compilazione**.

Configuriamo Remix per generare il **file dei metadata**.

 - Vai al modulo delle impostazioni cliccando sull’icona delle impostazioni ![settings](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/settings.png "Settings").

![impostazioni](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_settings.png "Settings Module")

 - E seleziona la prima opzione Generate `Generate contract metadata`.

# Compila e genera il file dei metadata (JSON).

1. Apri il Solidity Compiler ![Solidity Compiler](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_icon_solidity.png "Solidity Compiler")

2. Compile `2_contractSimpleLibrary.sol`.

3. Switch to the File Explorer ![File Explorer](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_file_explorer.png "File Explorer")

4. Navigate to the newly create JSON files.
    - It should be in the folder:

**browser/.learneth/DeployWithLibraries/2_Generate_Metadata/artifacts/**

5. Select the newly created JSON file created from the contract.  It has the **same name** as the contract `sample` but with the extension **json**: `sample.json` (don't select the library's metadata `contractSimpleLibrary.json`).

In the next step we'll make some adjustments to the metadata file.
