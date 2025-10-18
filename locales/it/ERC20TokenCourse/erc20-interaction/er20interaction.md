In questa sezione, distribuiremo un contratto nel nostro browser e testeremo le sue funzionalità.

### 1. Distribuisci il contratto

1.1 Compila il tuo contratto EduCoin nel modulo "Solidity compiler" dell'IDE Remix.

1.2 Nel modulo "Deploy & run transactions", seleziona il tuo contratto "EduCoin" nel campo di input del contratto e fai clic sul pulsante "Deploy". Assicurati sempre di selezionare il contratto corretto nel campo di selezione del.

Testa le funzioni

### 2. Testa le funzioni

Espandi le funzioni del contratto token nell'IDE.

#### 2.1 Decimali

Fai clic sul pulsante "decimals" per chiamare la funzione decimals().
Dovrebbe restituire "18".

#### 2.2 Nome

Fai clic sul pulsante "name" per chiamare la funzione name().
Dovrebbe restituire "EduCoin".

#### 2.3 Simbolo

Fai clic sul pulsante "symbol" per chiamare la funzione symbol().
Dovrebbe restituire "EDC".

#### 2.4 Offerta totale

Fai clic sul pulsante "totalSupply" per chiamare la funzione totalSupply().
Dovrebbe restituire 1000000000000000000000 (1000\*10\*\*18).

GIF Testa le funzioni decimals, name, symbol e totalSupply:

#### 2.5 Saldo di

2.5.1 Vai alla sezione "ACCOUNT" nella barra laterale e copia l'indirizzo visualizzato utilizzando l'icona di copia accanto ad esso.

2.5.2 Incolla l'indirizzo nel campo di input accanto al pulsante della funzione "balanceOf" e fai clic sul pulsante.
Dovrebbe restituire 1000000000000000000000 (1000\*10\*\*18).

GIF Testa la funzione balanceOf: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_balanceOf.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.6 Transfer

Trasferiremo EduCoin da un account a un secondo account.

2.6.1 Vai alla sezione "ACCOUNT" nella barra laterale e fai clic sull'indirizzo visualizzato. Questo dovrebbe aprire un menu a tendina. Seleziona il secondo indirizzo visualizzato e copia il suo indirizzo (account 2).

2.6.2 Apri il menu a tendina e seleziona nuovamente il primo account (account 1), perché questo è l'account che vogliamo utilizzare per effettuare il trasferimento.

2.6.3 Incolla l'indirizzo nel campo di input accanto al pulsante della funzione "transfer", inserisci il numero 500000000000000000000 e fai clic sul pulsante.

2.6.4 Se controlli i saldi per l'account 1 e l'account 2, entrambi dovrebbero restituire l'importo 500000000000000000000.

GIF Testa la funzione transfer: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_transfer.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.7 Approva

Ora consentiremo all'account 1 di spendere token per conto dell'account 2.

2.7.1 Vai alla sezione "Account", copia l'indirizzo dell'account 1, quindi impostalo nuovamente sull'account 2.

2.7.2 Nella funzione approve, inserisci l'indirizzo dell'account 1 come input per spender e imposta l'importo a 250000000000000000000.

GIF Testa la funzione approve: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_approve.gif?raw=true" alt="Test approve function" width="300"/>

#### 2.8 Allowance

Next to the "allowance" button enter the address of account 2 as the owner and account 1 as the spender; click on the button.
It should return 1000000000000000000000.

**GIF** Test allowance function: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_allowance.gif?raw=true" alt="Test allowance function" width="300"/>

#### 2.9 TransferFrom

Now account 1 will transfer 250000000000000000000 tokens from account 2 to its own account.

**2.9.1** Select account 1 in the "ACCOUNT" section.

**2.9.2** Next to the "transferFrom" button enter the address of account 2 as the sender and account 1 as the recipient, enter 250000000000000000000 as the amount and click on the button.

**2.9.3** Check the balances of accounts 2 and 1, they should return 250000000000000000000 and 750000000000000000000.

**GIF** Test transferFrom function: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_transferFrom.gif?raw=true" alt="Test transferFrom function" width="300"/>