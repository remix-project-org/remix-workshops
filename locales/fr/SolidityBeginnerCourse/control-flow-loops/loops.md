Solidity supports iterative control flow statements that allow contracts to execute code repeatedly.

Solidity différencie trois types de boucles : les boucles `for`, `while` et `do while`.

### for

Generally, `for` loops (line 7) are great if you know how many times you want to execute a certain block of code. In solidity, you should specify this amount to avoid transactions running out of gas and failing if the amount of iterations is too high.

### while

If you don’t know how many times you want to execute the code but want to break the loop based on a condition, you can use a `while` loop (line 20).
Loops are seldom used in Solidity since transactions might run out of gas and fail if there is no limit to the number of iterations that can occur.

### do while

The `do while` loop is a special kind of while loop where you can ensure the code is executed at least once, before checking on the condition.

### continue

The `continue` statement is used to skip the remaining code block and start the next iteration of the loop. Dans ce contrat, l'instruction `continuer` (ligne 10) empêchera la deuxième instruction if (ligne 12) d'être exécutée.

### break

The `break` statement is used to exit a loop. In this contract, the break statement (line 14) will cause the for loop to be terminated after the sixth iteration.

<0>Regardez un tutoriel vidéo sur les déclarations Loop</0>.

## ⭐️ Assignment

1. Create a public `uint` state variable called count in the `Loop` contract.
2. At the end of the for loop, increment the count variable by 1.
3. Try to get the count variable to be equal to 9, but make sure you don’t edit the `break` statement.