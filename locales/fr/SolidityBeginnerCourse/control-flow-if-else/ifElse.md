Solidity prend en charge différentes déclarations de flux de contrôle qui déterminent quelles parties du contrat seront exécutées. The conditional _If/Else statement_ enables contracts to make decisions depending on whether boolean conditions are either `true` or `false`.

Solidity differentiates between three different If/Else statements: `if`, `else`, and `else if`.

### if

The `if` statement is the most basic statement that allows the contract to perform an action based on a boolean expression.

Dans la fonction `foo` de ce contrat (ligne 5), l'instruction if (ligne 6) vérifie si `x` est inférieur à `10`. Si l'instruction est vraie, la fonction renvoie `0`.

### else

La déclaration `else` permet à notre contrat d'effectuer une action si les conditions ne sont pas remplies.

In this contract, the `foo` function uses the `else` statement (line 10) to return `2` if none of the other conditions are met.

### else if

With the `else if` statement we can combine several conditions.

Si la première condition (ligne 6) de la fonction foo n'est pas rencontrée, mais que la condition de l'instruction `else if` (ligne 8) devient vraie, la fonction renvoie `1`.

<a href="https://www.youtube.com/watch?v=Ld8bFWXLSfs" target="_blank">Regardez un tutoriel vidéo sur l'instruction If/Else</a>.

## ⭐️ Assignment

Créez une nouvelle fonction appelée `evenCheck` dans le contrat `IfElse` :

- That takes in a `uint` as an argument.
- The function returns `true` if the argument is even, and `false` if the argument is odd.
- Use a ternery operator to return the result of the `evenCheck` function.

Tip: The modulo (%) operator produces the remainder of an integer division.