Solidity fit support iterative control flow statementwey go allow contract to execute code repeatedly.

Solidity differentiates between di three types of loops: `for`, `while`, and `do while` loops.

### for

Generally `for` loops (line 7) dey great if u sabi how many times u want to execute a certain block of code. For solidity u fit specify dis amount to fit avoid transaction running out of gas and failing if di amount of iterations is too high.

### na while

If u no know how many times u wan execute di code but wan break di loop based on a condition u fit use `while` loop (line 20).
Loops dey seldom used for solidity since transactions fit run di gas and fail if dem no get limit of di number of iterations that can occur.

### do while

Di `do while` loop is a special kind of while loop where u can ensure the code is executed at least once, before u check on the condition.

### na to continue

Di `continue` statement is used to skip the remaining code block and start the next iteration of the loop. For dis contract di `continue` statement (line 10) will prevent the second if statement (line 12) from being executed.

### di break

Di `break` statement is used to exit a loop. Dis contract go break statement (line 14) will cause the for loop to be terminated after de sixth iteration.

<a href="https://www. youtube. com/watch? v=vTxxCbwMPwo" target="_blank"> Watch video wey go explain array</a>.

## When you give variable value

1. Create public `uint` state variable called count in de `Loop` contra.
2. At di end of di loop, increment the count variable by 1.
3. Try get di count variable to be equal to 9, but make sure you don’t edit the `break` statement.