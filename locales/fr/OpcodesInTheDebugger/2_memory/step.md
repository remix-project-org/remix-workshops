Before we start, just quick reminder:

The runtime of the EVM has several kinds of memory:

- `calldata`: This is the input value given to the transaction.
- `stack` : Fondamentalement, il s'agit d'une liste de valeurs, chaque valeur est limitée en taille (32 octets).
- `memory`: Memory is used when the **type** of value getting stored is more complex like an array or a mapping. Cette mémoire est **temporaire** et est **libérée** à la fin de l'exécution.
- `storage` : Il s'agit d'un mappage, chaque valeur stockée est **persistée** et enregistrée sur la chaîne.
