## How you go fit access functions inside contract wey dem don deploy

1. When dem don successfully deploy contract, e go appear under the Deploy and Run plugin. Click the caret make you fit open up the contract, so the caret go point down.
   ![deploy contract](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/instance.png "deployed contract")

2. 2 functions de inside this contract.  To enter the parameters one by one, you go click the caret wey dey the right near changeover (e dey written in red below). Inside view wey dey more wide, each parameter get him own input box.

![deploy contract](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/deployed_open2.png "deployed contract")

If this contract don bring other contract come, then the functions of the contracts wey him bring come go de visible for here.  If you don reach one side try use one ERC20 contract play you go see all the functions wey hin get.

3. Functions wey get blue buttons dem go be either \*\*pure or **view** functions.  This one mean say dem just dey read property or dem de return value.  You fit talk say, dem no de talk anything so dem dey FREE (they no de take gas).  Functions wey get other colour-normal normal na orange e de get (e de depend on the Remix theme) de cost gas because say dem dey save information.  Dem de create **transaction**.

4. 2_Owner.sol no get payable function.  E to say e get, the button colour for de red.  Payable functions de allow make you send Ether to the function.  To transfer eth wey get payable function, you go put the amount wey you wan send for the value field wey dey close to the top of the Deploy & run module.

5. For the remix vm, need no dey to approve transaction.  When you de use test environment wey dey more realistic or when you de use mainnet-you go need to approve transactions before dem fit go through. If you wan approve transaction e de cost gas.

6. Dem no de choose public network inside remix na inside your browser wallet dem de choose remix.  E get one plug icon wey dey the right of the environment title wey connect to chainlist.org where you fit get specs for the chain wey you wan interact with.
   ![chainlist](https://raw.githubusercontent.com/ethereum/remix-workshops/master/Basics/interacting/images/chainlist.png "chainlist")
