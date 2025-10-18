Di metadata extension no dey necessary. E dey gree make we fit add info join our ERC721 token. We fit put name, sign wit IRI (Uniform Resource Identifier) wey fit point go file wey we fit add info join as JSON.

## ERC721 Metadata Im Functions

### wetin dem dey call am

Di function `name` (line 16) wey dey return di name of di token collection. Token collection mean say all di token wey ERC721 create na token contract implementation. All di token wey dey dis collection go get dis name even with dem tokenld.

### sign

Di function `name` (line 21) wey dey return di name of di token collection.

### tokenURl

Di function `tokenURI` (line 26) dey return di URI for di token with di id `tokenId`. For dis case no be di everi collection but

## DE ERC721 Metadata JSON Schhema

De file dat de tokenURI points to te confirm to de Madeta JSON schemma as im dey specified for de <a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">EIP-721</a>.

```
"title": "Asset Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Identifies the asset to which this NFT represents"
        },
        "description": {
            "type": "string",
            "description": "Describes the asset to which this NFT represents"
        },
        "image": { type image/* representing the asset to which this NFT represents. Consider making any images at a width between 320 and 1080 pixels and aspect ratio between 1.91:1 and 4:5 inclusive."
        }
    }
}
            "type": "string",
            De description A URI pointing to resources wit im own mine
```

De root element must follow like de type object. Dis root object suppose get properties wey get keys: de nsme, de description, de image wey suppose be like all de type string.

De ERC0721 standard dey prety flexible de tokenURI no need to point to JSON document and de JSON no need make im get all properties and im always get additional properties.