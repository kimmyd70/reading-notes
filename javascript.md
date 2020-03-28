![parrot analogy pic](images/parrot.jpg)


# Javascript makes the action happen
## * updated class 2; Duckett 53-84

HTML is the content layer; CSS is the presentation layer; Javascript is the behavior layer forming *progressive enhancement* in a *step-by-step series of statements*

Use {}, '' (industry standard for js string), camelCase, escapes (Kim\'s)

**case sensitive** yellowHouse; See p 69 for variable naming rules

Remember the Construction Company website we coded with js
+ js in conditional statements that returned a greeting
+ declared the variables and conditions in a .js
+ called it with **script** in body of the html
+ our first instance of document.write function

runs (and prints to screen if applicable)where it is found in the html--remember if referenced in the HEAD, will likely run before page loads

use comments (//)

declare variable and assign value (same statement or separately)

var assignment can be an expression (eg: = 3 * 2)

use shorthand and operators for variable:
```
var price, quantity, total;
price = 5;
quantity = 15;
total = price * quantity;
```
(see Decisions and Loops for discussion of operators) 
+ Remember = vs == vs === (assigned, equal to, strictly equal)
+ String operators most often used is concatenation (eg: varOne + " ! " + varTwo)
    - pay attention to spacing and output format with concatenation

understand how the different types of variable interact (string, numeric, boolean)

Remember = vs == vs === (assigned, equal to, strictly equal)

### Arrays: variables storing more than one value

+ index starts at 0
+ if you use `indexOf.` function and it doesn't find the element it assigns index of -1              

```
var sammich;
sammich = ['bread', 'cheese', 'mayo']
```
then use the array in a function by calling by array *number*: 
`filling = sammich [1];` where the array numbering *starts at 0*

using array length as a variable:
```
var ingredients;
ingredients = sammich.length;
```
update array items:
```
sammich[2] = 'meat';
```