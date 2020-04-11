![function pic](images/Apple_slicing_function.png)


## *Updated with 106-144
## Functions see 86-99
+ group a series of statements together to perform a **specific** task
+ just enough code for that one thing
+ some need pieces of info called **parameters**
+ when you write a fn that gives a response that's a **return value**
+ return statement is not always needed
+ declaration using keyword: function.name() {stuff to do}
    - may have parameters
+ called with name(); parameters in the () as needed
+ **always start with lower case**
+ test in console log
+ can return single value (calculation) or multiple values (via array)
+ use function declaration for **named functions**

    - `function area (width, height)`
+ use function expression **with an argument** to call **anonymous function**
    - ` var area = function (width, height`)
    - saves return to the variable

+ immediately invoked function expressions (iify)
    - executed once interpreter reads
    - variable area holds the function return value
         ```
        var area =(function(){
            var width = 3;
            var height = 2;
            return width * height;
        }()) 
        //parenthesis pair ensures iffy
        //enclosing paren make it an expression
        ```
+ remember **local** vs **global** variables
    - local declared within a function and only accessible by that function

    - global outside function and anywhere within the script gives access to the script; consider declaring globals at the top of the document

    - global stored in memory (for as long as page is loaded) vs local used and discarded:  use local whenever possible

    - local can change value each time fn runs

    - different fun can use same name localvar without conflict



## *Updated with 106-144

Constructor notation:
```
var hotel = new Object();

hotel.name = 'Trump Tower';
hotel.rooms = 45;
hotel.booked = 0;

hotel.checkAvailable = function(){
    return this.rooms-this.booked;
};
```
update with ` hotel.name = 'Tower 2'` or `hotel ['name'] = 'Tower 2'`

+ Arrays and Objects create complex data sets
    - both can contain each other
    - remember Lab 06--global var array of objects must be declared AFTER object code
    - **See 118-119** for difference in how to access objects within arrays and vice versa

+  Look at JavaScript built-ins like **Window, String, Number, Math, Date** (see 124-139 for these)

    - Specify date and time with YYYY, MM, DD, HH, MM, SS or MMM DD, YYYY HH:MM:SS (w/wo time)

    - with MM = 0-11 DD = 1-31 HH = 0-23 MM = 0-59 SS = 0-59

    - if not specified, contains date and time of compillation

+ Create a Date Object with Constructor Notation
```
var today = Date();
```
then use **p137** for list of built in methods

+ Browser window itself is an object (containing objects)

+ see Reading notes on [object literals](object-literals.md)

+  **See p122-123 for Browser, Document, Global Javascript Built-in Objects**

+ Use `this.` within an object to refer to its properties 

