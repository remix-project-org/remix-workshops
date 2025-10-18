Nel capitolo precedente abbiamo compilato un contratto – cioè il codice Solidity è stato trasformato in piccoli blocchi di bytecode per la Ethereum Virtual Machine (EVM).

Ora metteremo quel codice su una blockchain di test.

1. Clicca sull’icona ![Deploy and Run](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_to_the_remixvm/images/run.png "deploy & run icon").

2. Seleziona una delle Remix VM dal menu a tendina Environment.

3. Clicca sul pulsante Deploy (o sul pulsante transact nella vista estesa).

4. Hai deployato il tuo contratto compilato nella Remix VM – una blockchain simulata che gira all’interno della finestra del tuo browser.  La Remix VM è una chain di test semplice e veloce.  Non è molto realistica perché non serve approvare ogni transazione.

5. Controlla il terminale per vedere i dettagli di questa transazione di deploy.

Puoi anche usare Remix per fare deploy su altre chain pubbliche EVM. Per farlo, dovrai connetterti a un Environment diverso – come Injected Provider.  L’Injected Provider collega Remix a un wallet del browser (come MetaMask o simili).  Proveremo a fare deploy su una rete pubblica alla fine di questo tutorial. Ma prima di arrivarci, vedremo come interagire con le funzioni di un contratto deployato.
