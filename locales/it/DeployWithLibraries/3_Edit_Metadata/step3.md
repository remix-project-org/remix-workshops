La proprietà `Deploy` in `sampleContract.json` contiene tutto ciò di cui hai bisogno per dire a Remix IDE l’indirizzo della libreria per una rete specifica.

- <address> contiene l’indirizzo della libreria che è già stata deployata. Devi specificare questo indirizzo per ogni rete.
- `autoDeployLib` è un booleano e indica a Remix IDE se deve fare l’autodeploy della libreria prima di fare deploy del contratto.

In pratica, se `autoDeployLib` è **true**, <address> non verrà usato e Remix deployerà automaticamente la libreria prima di deployare il contratto.

Ai fini di questa demo – stiamo simulando una situazione in cui la libreria è già stata deployata, perché è lo scenario più comune.

Quindi imposta `autoDeploy` su **false**, per la voce VM:-.

Move to next Step.
