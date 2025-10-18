# Modification d'un scénario

Voici les premières lignes du scénario que j'ai enregistré.  Les adresses sur ma machine seront différentes des vôtres.

```
{
    "accounts": {
    "account{0}": "0xca35b7d915458ef540ade6068dfe2f44e8fa733c",
    "account{4}": "0xdd870fa1b7c4700f2bd7f44238821c26f7392148",
    "account{3}": "0x583031d1113ad414f02576bd6afabfb302140225"
    }
```

So if you wanted to play this scenario in another testnet, you'd need to change these addresses to address that you have test ETH on so that you could pay for the transactions.  Mais en plus d'échanger les adresses, vous pouvez rapidement l'exécuter sur d'autres réseaux.

And you might change the parameters for the functions.

Par exemple, voici un peu du scenario.json un peu plus bas où la proposition 2 a été votée par l'une des adresses :

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

Modifions ceci pour qu'une autre proposition gagne dans la lecture.

Change the **parameters** array which now is:

```
"parameters": [
          "2"
        ]
```

à:

```
"parameters": [
          "1"
        ]
```
