D ERC20 standard dey only describe di required and optional functionality way yur contract need, but you fit add additional functionality.

Inside dis section, we don add d functionality to burn and mint tokens, as well as di ability to pause di contract, as we use OpenZeppelin extensions.

Naso, you fit write your own ERC20 token contract implementation or extensions nd dit import them put for yur contract. But security experts don audit OpenZeppelin contracts and dem b nice connect to add functionality wey yu like.

### Mintable

D mint function dey allow di creator of di contract to mint (create) additional tokens after dem don deploy d contract (line 22). As na input parameters, the function go need di address wey di tokens go dey minted to, and the amount of tokens wey suppose dey minted.

We no need to import `mint()` from another contract since di mint function na already part of di <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol" target="_blank">ERC20 contract</a> implementation of OpenZeppelin. We dey import `Ownable` (line 7) wey be contract module wey dey provide basic access control mechanism wey dey allow owner to get exclusive access to specific functions. Inside dz contract, we don add di inherited `onlyOwner` modifier to di `mint` function (line 22) and we don restrict access to dis function to di "owner".

The contract go inherit additional functions like owner(), transferOwnership() nd renounceOwnership() to manage access, from di <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/access/Ownable.sol" target="_blank">Ownable contract</a>.

### Burnable

Once yu import di "ERC20Burnable" (line 5) nd yu inherit hin functions (line 9) our contract go allow token holders fit destroy their tokens as well as di tokens wey dey dia allowance.
If yu wan more information, look di <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/extensions/ERC20Burnable.sol" target="_blank">ERC20Burnable contract</a>.

### Pausable

With di "Pausable" contract module (line 6 and 9) the owner go fit to pause (line 14) and unpause (line 18) di contract. In the pause state, tokens can't be transferred, which can be helpful in emergency scenarios.
For more information, have a look at the <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/security/Pausable.sol" target="_blank">Pausable contract</a>.

Have a look at the OpenZeppelins <a href="https://docs.openzeppelin.com/contracts/4.x/wizard" target="_blank">Contract Wizard</a>, which allows you to easily add additional functionality.

If you successfully completed this course, try the Learneth NFT Course as the next step in your journey.

## ⭐️ Assignment

1. Try to mint tokens to an account after deployment. Call `totalSupply()` and `balanceOf()` to confirm the correct execution.
2. Burn tokens and then call `totalSupply()` and `balanceOf()` to confirm the correct execution.
3. Test the pause function by pausing the contract using the owner account and trying to make a transfer with a second account. The transaction should not be able to be executed and will throw the exception: "Pausable: paused".
