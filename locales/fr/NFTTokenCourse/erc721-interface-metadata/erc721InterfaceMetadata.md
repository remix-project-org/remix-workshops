The metadata extension is optional. It allows us to add additional information to our ERC721 tokens. We can specify a name, a symbol, and an URI (Uniform Resource Identifier) that can point to a file where we can add even more information in the form of a JSON.

## ERC721 Metadata Functions

### name

La fonction `name` (ligne 16) renvoie le nom de la collection de jetons. Une collection de jetons désigne tous les jetons créés avec la mise en œuvre de votre contrat de jeton ERC721. Every token in this collection will have this name, regardless of their tokenId.

### symbol

The function `symbol` (line 21) returns the symbol of the token collection.

### tokenURI

The function `tokenURI` (line 26) returns the URI for the token with the id `tokenId`. In this case it’s not the URI of the whole collection but of an individual token in the collection.

## Schéma JSON de métadonnées ERC721

Le fichier vers lequel le tokenURI pointe doit être conforme au schéma JSON de métadonnées tel qu'il est spécifié dans le <0>EIP-721</0>.

```
{
    "title": "Asset Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Identifie l'actif que ce NFT représente"
        },
        "description": {
            "type": "string",
            "description": "Décrit l'actif que ce NFT représente"

},
        "image": {
            "type": "string",
            "description": "Un URI pointant vers une ressource avec une image de type mime/* représentant l'actif que ce NFT représente. Envisagez de créer des images d'une largeur comprise entre 320 et 1080 pixels et un rapport d'aspect compris entre 1,91:1 et 4:5 inclus."
        }
    }
}
```

The root element must be of the type object. This root object should have properties with the keys: name, description, and image that should be all of the type string.

The ERC721 standard is pretty flexible, the tokenURI does not need to point to a JSON document and the JSON does not need to have all properties and often has additional properties.