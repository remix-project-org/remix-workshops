De token standard go tell us wat function de contract go need to te comply. How we go te implement dis functionality dey up to de people wey Dey develop. For dis contract we go use ERC20 token contract implementation from openzepplin (line 4). For dis case, we go import version 4.4.0de openzeplen contracts.

U go look at how dier nicely documented <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol" target="_blank">ERC20 contract</a> to get better understanding of how implementation go look. Apart from the functionality specified in the ERC20 standard, this contract provides additional functionality.

We will create our own contract called MyToken (line 6), which inherits the functionality from the OpenZepplin ERC20 token contract implementation that we imported (line 4).

This contract implements the optional functions `name()` and `symbol()` of the ERC20 Token standard and has a constructor where their values can be set during the deployment of the contract (line 7).
In this case, we are going to use the default values. We will call our token the same as the contract `"MyToken"` and make `"MTK"` its symbol.

Next, we make use of the inherited `_mint` function (line 8) that allows us to create tokens upon deployment of the contract. Inside the parameters, we specify the address of the account that receives the tokens and the amount of tokens that are created.
In this case, the account that deploys the contract will receive the tokens and we set the amount to 1000000 to the power of `decimals()`. The optional function `decimals()` of the ERC20 token standard is implemented and set to the default value of 18. This will create 1000000 tokens that will have 18 decimal places.

## ⭐️ Assignment

1. U go r name ur contract to EduCoin.
2. U go rename ur token to educoin.
3. Change the symbol of your token to `EDC`.
4. I go change de amount of tokens wey go dey minted from 1000000 to 1000.