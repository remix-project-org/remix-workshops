For this section, we go deploy contract for our browser con test the functionality.

### 1. Deploy the contract

1.1 Compile your EduCoin contract for "Solidity compiler" module wey dey Remix IDE.

1.2 for the Deploy & run transactions module, tap on your contract "EduCoin" for the contract input field con click the "Deploy" button. Always make sure say you select the correct contract for the contract selector input field.

**GIF** Compile and deploy: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_compileAndDeploy.gif?raw=true" alt="Compile and deploy contract" width="300"/>

### 2. Test run the functions

Expand the token contract functions for the IDE.

#### 2.1 Decimals

Click on the "decimals" button if you wan call the decimals() function.
E suppose return "18".

#### 2.2 Name

Click the name button to call the name() function.
E suppose return "educoin".

#### 2.3 Symbol

Click the Symbol button if you wan call the symbol() function.
E suppose return "edc".

#### 2.4 Total supply

Click the totalsupply button if you wan call the totalsupply() function.
E suppose return 1000000000000000000000 (1000\*10\*\*18).

**GIF** Test decimals, name, symbol, and totalSupply functions: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_test_functions.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.5 Balance of

2.5.1 Go the "ACCOUNT" section wey dey the sidebar con go copy the address wey dem display by using that copy icon wey dey next to am.

2.5.2 Paste the address go the input field wey dey near the "balanceOf" function button con click the button.
E suppose return 1000000000000000000000 (1000\*10\*\*18).

GIF Test balanceOf function: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_balanceOf.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.6 Transfer

We go transfer educoin from one account go another account.

2.6.1 Go to "ACCOUNT" section for the sidebar con click the address wey dey show. E suppose open one dropdown. Select the second address wey you dey see con copy the adddess(account 2).

2.6.2 Open the dropdown con select the first account again (account 1), based on say this na the account wey we wan use take do the transfer.

2.6.3 Paste the address go the input field wey dey close to the "transfer" function button, con input the number 500000000000000000000, con click the button.

2.6.4 If you don check the balance for account 1 and account 2, dem suppose return 500000000000000000000.

GIF Test transfer function: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_transfer.gif?raw=true" alt="Test transfer function" width="300"/>

#### 2.7 Approve

Na now we go allow account 1 spend tokens in place of account 2.

2.7.1 Go the "Account" section, copy address of account 1, con set am to account 2 again.

2.7.2 for the approve function, write the address of account 1 as input for spender con set the amount go 250000000000000000000.

GIF Test approve function: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_approve.gif?raw=true" alt="Test approve function" width="300"/>

#### 2.8 Allowance

Close to that allowance button write the address of account 2 say na the owner and account 1 say na the spender, con click the button.
E suppose return 1000000000000000000000.

GIF Test allowance function: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_allowance.gif?raw=true" alt="Test allowance function" width="300"/>

#### 2.9 TransferFrom

Now account 1 go transfer 250000000000000000000 tokens from account 2 come e own account.

2.9.1 Select account 1 for the "ACCOUNT" section.

2.9.2 close to the "transferFrom" button write the address of account 2 say e be the sender and account 1 say na recipient, enter 250000000000000000000 as the amount con click the button.

2.9.3 observe the balances of accounts 2 and 1, dem suppose return 250000000000000000000 and 750000000000000000000.

GIF Test transferFrom function: <img src="https://github.com/dacadeorg/remixMedia/blob/main/token-course/erc20/erc20_transferFrom.gif?raw=true" alt="Test transferFrom function" width="300"/>