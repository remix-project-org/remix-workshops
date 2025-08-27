## Accedere alle funzioni in un contratto deployato

1. Quando un contratto è stato deployato con successo, apparirà in fondo al plugin Deploy and Run. Apri il contratto cliccando sulla freccetta – così che punti verso il basso.
   ![distribuisci il contratto](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/instance.png "contratto distribuito")

2. Ci sono 2 funzioni in questo contratto.  Per inserire i parametri singolarmente, clicca sulla freccetta a destra di changeOwner (evidenziata in rosso qui sotto). Nella vista estesa, ogni parametro ha la sua casella di input.

![deploy contract](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/deployed_open2.png "deployed contract")

Se questo contratto avesse importato altri contratti, anche le funzioni dei contratti importati sarebbero visibili qui.  A un certo punto, prova a sperimentare con un contratto ERC20 per vedere tutte le sue numerose funzioni.

3. Le funzioni con i pulsanti blu sono funzioni pure o view.  Questo significa che si limitano a leggere una proprietà o a restituire un valore.  In altre parole, non salvano nulla – quindi sono GRATUITE (non costano gas).  Le funzioni con altri colori – solitamente arancione (a seconda del tema di Remix) – costano gas perché salvano informazioni.  Stanno creando una transazione.

4. 2_Owner.sol does not have a **payable** function.  If it did, the button's color would be red.  Payable functions allow you to send Ether to the function.  To send ETH with a payable function, you put the amount you want to send in the **value** field towards the top of the Deploy & Run module.

5. In the Remix VM, you don't need to approve a transaction.  When using a more realistic test environment or when using the mainnet - you will need to approve the transactions for them to go through. Approving a transaction costs gas.

6. Choosing a public network is not done in Remix but in your Browser Wallet.  There is a plug icon to the right of the Environment title that links to chainlist.org where you can get the specs of the chain you want to interact with.
   ![chainlist](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/chainlist.png "chainlist")
