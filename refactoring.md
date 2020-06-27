## Refactoring and Functional Coding

[Medium article](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

(if link doesn't work without paid subscription, see .pdf in repo)

[Dev.to article](https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec)

_______

### Medium Article

visit the author's [Functional Programming Github repository](https://github.com/leandrotk/functional-programming-learning-path)

+ Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia

+ So how do we know if a function is pure or not? Here is a very strict definition of purity:
It returns the same result if given the same arguments (it is also referred as deterministic)
It does not cause any observable side effects

    - If our function reads external files, it’s not a pure function — the file’s contents can change.

    - Any function that relies on a random number generator cannot be pure.

    - Examples of observable side effects include modifying a global object or a parameter passed by reference. 
    
    Better:
    `const increaseCounter = (value) => value + 1;
    `

+ Avoid: When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.

+ With recursion, we keep our variables immutable. The list and the accumulator variables are not changed. It keeps the same value.

```
sum(list, accumulator); // 15
list; // [1, 2, 3, 4, 5]
accumulator; // 0
```

### pure functions + immutable data = referential transparency

+ The idea of functions as first-class entities is that functions are also treated as values and used as data.
Functions as first-class entities can:

    - refer to it from constants and variables

    - pass it as a parameter to other functions

    - return it as result from other functions

+ The idea is to treat functions as values and pass functions like data. This way we can combine different functions to create new functions with new behavior.

+ The map method transforms a collection by applying a function to all of its elements and building a new collection from the returned values.

_______

### Dev.to article on Refactoring for performance and readability 

Strategies:

+ Return early from functions

+ Cache variables so functions can be read like sentences

+ Check for Web APIs before implementing your own functionality



