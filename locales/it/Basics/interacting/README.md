## Accedere alle funzioni in un contratto deployato

1. Quando un contratto è stato deployato con successo, apparirà in fondo al plugin Deploy and Run. Apri il contratto cliccando sulla freccetta – così che punti verso il basso.
   ![distribuisci il contratto](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/instance.png "contratto distribuito")

2. Ci sono 2 funzioni in questo contratto.  Per inserire i parametri singolarmente, clicca sulla freccetta a destra di changeOwner (evidenziata in rosso qui sotto). Nella vista estesa, ogni parametro ha la sua casella di input.

![deploy contract](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/deployed_open2.png "deployed contract")

Se questo contratto avesse importato altri contratti, anche le funzioni dei contratti importati sarebbero visibili qui.  A un certo punto, prova a sperimentare con un contratto ERC20 per vedere tutte le sue numerose funzioni.

3. Le funzioni con i pulsanti blu sono funzioni pure o view.  Questo significa che si limitano a leggere una proprietà o a restituire un valore.  In altre parole, non salvano nulla – quindi sono GRATUITE (non costano gas).  Le funzioni con altri colori – solitamente arancione (a seconda del tema di Remix) – costano gas perché salvano informazioni.  Stanno creando una transazione.

4. 2_Owner.sol non ha una funzione payable.  Se l'avesse, il colore del pulsante sarebbe rosso.  Le funzioni payable consentono di inviare Ether alla funzione.  Per inviare ETH con una funzione payable, inserisci l'importo che desideri inviare nel campo value verso la parte superiore del modulo Deploy & Run.

5. Nella Remix VM, non è necessario approvare una transazione.  Quando si utilizza un ambiente di test più realistico o la mainnet, sarà necessario approvare le transazioni affinché vengano completate. Approvare una transazione costa gas.

6. La scelta di una rete pubblica non avviene in Remix, ma nel tuo Browser Wallet.  C'è un'icona a forma di spina a destra del titolo Environment che collega a chainlist.org, dove puoi ottenere le specifiche della chain con cui desideri interagire.
   ![chainlist](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/chainlist.png "chainlist")
