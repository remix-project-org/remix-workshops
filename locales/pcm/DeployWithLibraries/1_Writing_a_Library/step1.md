A libraries resemble **contract** but e dey use d keyword `library`

A library na typically collection of functions wey useful wey jst dey sidown out there on d blockchain way any contract fit use.  Because say the library don dey deployed e go save the deployment costs of the amount of contracts wey dey use am.

For the contract wey dey follow:

- Use the name make one library `LibraryForTest`.

E dey possible make u put a library for the same file with another contract.  Oya carry the library put below the contract.

This library should have a method called `getFromLib` method which returns `3`.

- Update the `get` method in the `test` contract to use the `LibraryForTest` library.   The function `get` should return the value it receives from `getFromLib`.

---------

You can find more info about libraries in <a href="https://solidity.readthedocs.io/en/latest/contracts.html?highlight=library#libraries" target="_blank">this section of the Solidity Docs</a>.
