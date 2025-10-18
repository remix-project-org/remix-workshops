# Comment ça marche ?

**EIP-7 DelegateCall** opcode permet une exécution séparée dans un autre contrat tout en conservant le contexte d'exécution d'origine.

Tous les **appels de message** de l'utilisateur passent par un **contrat de proxy**.

Le **contrat de proxy** les redirigera ensuite vers le **contrat logique**.

Et lorsque vous avez besoin de **mettre à niveau** la logique, vous allez **seulement** déployer que - **CEFFois** - l'implémentation de Proxy restera la même.

You'll only need to update the address of Logic contract in Proxy.

Le contrat de proxy utilise **appels délégués** et **assemblage de solidité** car sans cela, il est impossible de renvoyer une valeur de **delegatecall**.
