De token standard go tell us wat function de contract go need to te comply. How we go te implement dis functionality dey up to de people wey Dey develop. For dis contract we go use ERC20 token contract implementation from openzepplin (line 4). For dis case, we go import version 4.4.0de openzeplen contracts.

U go look at how dier nicely documented <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol" target="_blank">ERC20 contract</a> to get better understanding of how implementation go look. Apart from di functionality specified in di ERC20 standard dis contract provides additional functionality.

We fit still create our own contract called MY TOKEN (line 6), which inherits the functionality from the OpenZepplin ERC20 token contract implementation that we imported (line 4).

Dis contract implement di optional functions `name()` and `symbol()` of di ERC20 Token standard and has a constructor where their values c fit set during the deployment of the contract (line 7).
For dis case we go use di default value. We fit call our token di same as di contract `"MyToken"` and make `"MTK"` its symbol.

Next we fit make use of di inherited `_mint` function (line 8) that allows us to create tokens upon deployment of the contract. For di inside di parameter, we fit address di account wey dey recieves di token and di amount of di token dat are created.
For dis case di account wey deploys di contract will receive di token and we donn set di amount to 1000000 to the power of `decimals()`. Di optional function `decimals()` of the ERC20 token standard is implemented and set to the default value of 18. Dis fit create 1000000 tokens that will have 18 decimal places.

## De Asignment

1. U go r name ur contract to EduCoin.
2. U go rename ur token to educoin.
3. Change the symbol of your token to `EDC`.
4. I go change de amount of tokens wey go dey minted from 1000000 to 1000.