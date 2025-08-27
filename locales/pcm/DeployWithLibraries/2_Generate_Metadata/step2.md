## Deploying Library

The library wey dey the previous chapter dey the same file as the contract. But still, dem no go dey deployed together and dem go get different addresses.

Before you fit use any library, the calling contract must get the library address.

But he library address no dey directly specified for the solidity code. The calling contract compiled bytecode dey get placeholder where be say library addresses go go.

As you dey deploy the calling contract, remix go check inside the contract metadata for the library address and e go con update the placeholder with the address.

So before deploying contract wey dey calm library, you gats generate the contract metadata (aka the build artifact) and then you gats con input the library address inside the metadata file.

Metadata for contract dey generated at compile time.

Make we setup remix to take generate the metadata file.

- Go the settings module by clicking on settings![settings](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/settings.png "Settings") icon for the icon panel.

![settings module](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_settings.png "Settings Module")

- Con check the first option `Generate contract metadata`.

# Compile con generate the metadata (JSON) file.

1. You go open the Solidity Compiler ![Solidity Compiler](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_icon_solidity.png "Solidity Compiler")

2. Compile `2_contractSimpleLibrary.sol`.

3. Switch go file explorer ![File Explorer](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/2_Generate_Metadata/remix_file_explorer.png "File Explorer")

4. Scroll go the json file wey you just create.
    - E suppose dey the folder:

browser/.learneth/DeployWithLibraries/2_Generate_Metadata/artifacts

5. Pick the json file wey you just create from the contract.  E get the same name as the contract sample but with the extension **json**: `sample.json` (don't select the library's metadata `contractSimpleLibrary.json`).

For the next step we go do some changes for the metadata file.
