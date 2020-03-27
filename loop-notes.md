![venn diagram](images/ops.png)

## *Updated for class 3

## Comparison *Operators* (as in comparative logic courses taken before)

**Six operators:**
+ == **equal** to (3 and '3' will return true)
+ === **strictly equal** more useful; same info, same type
+ ! **not** added to equal or se
+ >, <, >=, <= as in math
+ && **logical and**
+ || **logical or**
+ += is same as msg = msg + new msg (see p176)

+ also *= which is 6*=5 --> 30

**Using if comparison statement:**
``` 
if (score >=50){
    //call function or do action
    congratulate(); 
}
else if {
    //note use of ;
    encourage(); //not necessary
}
else {
    //use safety catch all or maybe "try again" loop--not necessary
}
```

**Loops:** check a condition, true runs the code block, check again, true runs code block...until false

+ **for** specify number of times (counter)
+ **while** condition something other than a counter and runs as long as condition remains true (could run zero times)
+ **do while** like while but always runs once even if first run evals to false

for (var i=0; i <1 0; i++) {do stuff}
+ **initializes** i to 0
+ checks to see if **condition** i is < 0 is true
+ **runs the block of code**
+ **updates** by incrementing i by 1
+ re-runs until i !< 0

See p 172-173 for pictoral of the above loop

while(i < 10) {do stuff}
+ runs until i = 10
+ need i++ or other increment in "do stuff"
+ postion of increment in "do stuff" is important (check intended flow)


**Switch statements:** gives cases to assign value to a variable
+ must contain a default case!

```
var level; <!--get this assigned from input or other; in this example, level = integer>

switch (level) {
case 1:
  do stuff

case 2:
  do stuff

case 3:
  do stuff

default:
necessary to have catch all
}
```
**Type Coercion**: js will always try to make sense of an operation vs erroring out in erroneous expressions such as '1' > 0

NaN (' ') = false because evaluates to **zero** which IS a number (use isNaN built in function)

`'use strict';` helps avoid type coercion as does using === in expressions

**Truthy/Falsy (p168):** values treated "as if" they evaluate to true or false; may cause unintended
+ Falsy: empty values/null string, NaN, not assigned value, the number zero, and boolean false are all evaluated as "false"--treated as 0

+ Truthy: value > 0; string with content, number calculation ( except /0; as in Math), 'true', '0', 'false', and boolean true are all evaluated as "true"--treated as 1

+ NaN is considered falsy and NOT equivalent to anything, even itself

**Short Circuit Values:** processing left to right and stopping as soon as there is a result.  Return the value that stopped the process
+ best to put the *most likely* **true** return in || and first **false** return in && 
+ put operations requiring the most computing power (expression) last because it may not need to run

**Unitary Operator:** expression with one operand (function, for example) returns truthy/falsy and will not evaluate the same as if the operand is set == true or == false (AVOID)