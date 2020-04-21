![bugs](bugs.jpg)

## Debugging (pp 449-486)

+ Uses the process of deduction

+ Console logging is helpful for methodical approach

+ Know the order of script execution

+ Know the execution context: global or function

+ Understand how the stack works:

![The stack](stack1.png)

![The stack](stack.png)

+ Each time script enters new execution context:
    - Prepare
        - create new scope
        - create variables, functions, arguments
        - determine the value of `this`
    - Execute
        - assign values to variables
        - reference functions and run their code
        - execute statements

+ For Scope, Remember: what happens in Vegas

+ Seven types of error objects:
    - Error (generic)
    - SyntaxError
    - ReferenceError (undeclared var)
    - TypeError (can't be coerced)
    - RangeError (numbers)
    - URIError (encode or decode URI)
    - EvalError (eval fn used incorrectly)

+ Workflow: Where and What
    - where: relevant script, line number, type of error, check how far script runs, use breakpoints

    - what: write values into variables, call fn from the console, check if objects correct, check fn parameters, repeat

+ Can write `console.table()` for clarity in TS
+ Can write `console.assert()` to test condition (writes if false)
+ Set breakpoints in Chrome: Sources > click on line # in script; can set conditional (only stops on line # if true)

+ Can use 
```
try{
    //code to be tested
} catch (exception){
    //run this for exception
} finally {
    // always executes
}
```
0r
 
 `throw new Error ('message');` especially for NaN

 ![Debugging Tips](debugging.png)

 ![Common Errors](common-errors.png)




