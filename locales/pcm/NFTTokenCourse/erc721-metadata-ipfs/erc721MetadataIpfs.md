For dis section, we go create our metadata come store am for decentralised way.

IPFS ( InterPlanetary File System) na peer-to-peer network to take store files for distributed way. Pinata.cloud na pinning service wey dey allow make users fit easily host files for di IPFS network.

We wan host sea image and di JSON files wit dem metadata for IPFS.

### Come create picture folder

For dis example, we go create metadata for three tokens. As you dey see for down, we dey create picture wey be three wey we store for folder.

```
geo-img
├── geo_1.png
├── geo_2.png
├── geo_3.png
```

### You go register for Pinata

Like dis we wan host dis picture for one place so we go fit point give dem for di metadata of awa tokens. Make we do am for decentralised way make we use Piñata take host dem for IPFS.

First you go need akant for Pinata. Go <a href="https://app.pinata.cloud/register" target="_blank">Pinata.cloud</a> come create akant. For pinata you fit upload reach 1 Gb of data for free.

Once you don sign up, you suppose dey di Pin Manager view.

<img src="https://i.imgur.com/yKpD65m.png" alt="Pin Manager Pinata" width="300"/>

### Upload Pictires go IPFS

Click di upload button make you oo load folder wit your pictures.
Once you don upload your folder you suppose see di name of your folder and di CID (content identifier) wey dey associated with am. If di contend wey dey folder change, di CID sef go change.

To fit reach your folder wey dey IPFS, enta dis address
"https://ipfs.io/ipfs/" make you add your CID. For our example now now, you go access your folder if you dey use <a href="https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P" target="_blank">
https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P </a>

You fit reach one kind image if you dey use: <a href="https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png" target="_blank">
https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png </a>

### Go create JSON files

We go do anoda folder wey we store three JSON files.

```
geo-json
├── 0
├── 1
├── 2
```

Inside di JSON files, create di metadata for di tokens, like name, description, and image.
For di image URL, we dey go use di URL of our images on IPFS. You fit add data join if you like: for dis example we don add some kind fine attributes go each token.

Na like how do JSON for di first token go be:

```
{
    "name": "Geometry#0",
    "description": "Geometry is an NFT collection for educational purposes.",
    "image": "https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png
",
    "attributes": [
        { "trait_type": "background", "value": "cyan" },
        { "trait_type": "color", "value": "red" },
        { "trait_type": "shape", "value": "circle" }
    ]
}
```

Na like how di JSON for di second token go be like:

```
{
    "name": "Geometry#1",
    "description": "Geometry is an NFT collection for educational purposes.",
    "image": "https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_2.png",
    "attributes": [
        { "trait_type": "background", "value": "magenta" },
        { "trait_type": "color", "value": "green" },
        { "trait_type": "shape", "value": "square" }
    ]
}
```

As dem show am for up, di folder wey dey dis example dem dey call am geojson. Insid dis folder we get three JSON files.
Di first JSON file dem dey call am “0", di second JSON file dem dey call "1" and di third JSON dem dey call am "2".

Ensure say your JSON files no get file ending and dem name dem like dem corresponding tokenlds.
For di pin manager for pinata.cloud, click for di upload button make you come upload di folder with.

To fit access your folder for IPFS, enta dis adress
"https://ipfs.io/ipfs/" and add your CID.
For our example now now, you go access your folder if you dey use<a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp" target="_blank">
https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqpThis
</a>.

You fit access one kind JSON file den you go just dey add slash and di tokenld wit <a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/0" target="_blank">
https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/0 </a>

For dis contrakt, commot di baseURL wit your own baseURL. For dis example di baseURl e consist of di URL
"https://ipfs.io/ipfs/", di CID wey dey contain di JSON files and slash for di end "/".

An individual tokenURI will now be created for each token by adding the tokenId to the baseURI — exactly what we did manually in the example above to access the JSON file.
