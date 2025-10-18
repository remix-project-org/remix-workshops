1. Se non hai un wallet per browser come MetaMask, scaricalo e installalo ora.

2. Clicca sull’icona di MetaMask nel tuo browser. Accedi e scegli la rete di test Ephemery. Potresti dover aggiornare le impostazioni del tuo wallet per poter visualizzare le reti di test.  In alternativa, puoi andare nel modulo Deploy & Run di Remix e nella sezione ENVIRONMENT selezionare Ephemery.

3. Ottenere ETH di test per le reti pubbliche di test è spesso fastidioso.  Ephemery è una rete pubblica che viene aggiornata mensilmente, quindi ottenere ETH di test dovrebbe essere semplice.  Ecco un link ad alcuni <a href="https://github.com/ephemery-testnet/ephemery-resources?tab=readme-ov-file#faucets" target="_blank">faucet di Ephemery</a>.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/testnet.png)

Sepolia è un’altra testnet popolare che non viene aggiornata, quindi i deploy rimarranno, ma i faucet di Sepolia sono più difficili da usare.

Nel tuo wallet del browser assicurati di NON aver selezionato mainnet o qualsiasi rete che richieda ETH reali. Nel modulo Deploy & Run, sotto il menu a tendina Environment, vedrai un badge con l’ID della rete e, per le catene più popolari, il loro nome.  Nel caso qui sotto è Sepolia.

![](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/deploy_injected/images/sepolia.png)

5. Assicurati di vedere 2_Owner.sol come opzione nel menu a tendina CONTRACT, poi clicca il pulsante Deploy.

Se il menu a tendina **CONTRACT** è vuoto, dovrai compilare di nuovo 2_Owner rendendo 2_Owner.sol il file attivo nell’**editor** e poi andando nel **Solidity** Compiler per compilarlo.

6. Dopo aver cliccato sul pulsante `Deploy`, vedrai apparire il popup del wallet del browser che ti chiederà di pagare per le transazioni.  Se hai il tipo corretto di ETH per questa chain, approva la transazione.  Controlla l’output nel terminale.  Una volta che il blocco è validato, **l’istanza deployata** apparirà in fondo a Deploy & Run

E con questo hai completato il tutorial.  Ora hai esperienza nell’aprire, compilare, deployare e interagire con Smart Contract in Remix IDE.
