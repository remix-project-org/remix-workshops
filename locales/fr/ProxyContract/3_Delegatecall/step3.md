# Appel de délégué

C'est une variante spéciale d'un **appel de message**, qui est identique à un appel de message mis à part le fait que le code à l'adresse cible est exécuté dans le contexte du contrat d'appel afin que **msg.sender** et **msg.value** ne changent pas leurs valeurs.

Cela signifie qu'un contrat peut charger dynamiquement du code à partir d'une adresse différente au moment de l'exécution.

The storage, the current address and balance still refer to the calling contract, only the code is taken from the called address.

So when a **Proxy** delegates calls to the Logic contract, every storage modification will impact the storage of Logic contract.