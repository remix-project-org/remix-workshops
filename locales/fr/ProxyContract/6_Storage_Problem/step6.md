# Et si nous avons des variables d'état ?

Things are more complicated once we need to deal with state variables.  State variable are saved to **storage**.

`stockage` : est un mappage ; chaque valeur stockée y est conservée et enregistrée sur la chaîne.

_Note: Statically-sized state variables (everything except mapping and dynamically-sized array types) are laid out contiguously in storage starting from position 0. Plusieurs éléments contigus qui ont besoin de moins de 32 octets sont regroupés dans un seul emplacement de stockage si possible. Pour les contrats qui utilisent l'héritage, l'ordre des variables d'état est déterminé par l'ordre linéaire C3 des contrats commençant par le contrat le plus basé_

Once we execute **delegate call**, the storage of both contracts get **"merged"** into a single messy state.

We have to "tell" ProxyContract what the **state** of the **Logic contract** looks like.

The easiest way to do this is to create a separate contract - in this example - named **StorageContract** which will represent the **state** and which proxyContract will inherit from.
