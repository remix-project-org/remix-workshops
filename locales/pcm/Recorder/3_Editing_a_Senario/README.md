# Editing de scenario

Na the first few lines of the scenerio wen I record.  De addresses for my machine go dey different from ur own.

```
{
    "accounts": {
    "account{0}": "0xca35b7d915458ef540ade6068dfe2f44e8fa733c",
    "account{4}": "0xdd870fa1b7c4700f2bd7f44238821c26f7392148",
    "account{3}": "0x583031d1113ad414f02576bd6afabfb302140225"
    }
```

So if u want play dis scenario for another testnet, u go need change de addresses to address wen u go test ETH on so u go pay for de transactions.  Apart to dey swap the addresses, u fit quickly run dis for other nets.

U fit change de parameters for de functions.

For example here na a bit of de scenario.json a bit further down where dey vote proposal 2 for by one of the addresses:

```
{
      "timestamp": 1566428184043,
      "record": {
        "value": "0",
        "parameters": [
          "2"
        ],
        "to": "created{1566428035436}",
        "abi": "0xc41589e7559804ea4a2080dad19d876a024ccb05117835447d72ce08c1d020ec",
        "name": "vote",
        "inputs": "(uint8)",
        "type": "function",
        "from": "account{4}"
      }
    },
```

Make we dis make another proposal win for the playback.

Make we change the **parameters** array which be now:

```
"parameters": [
          "2"
        ]
```

to:

```
Di "parameters": [
          "1"
        ]
```
