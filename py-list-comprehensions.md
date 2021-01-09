## List Comprehensions

notes from [this article](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

 Provides a concise way to create lists

 For example: `new_list = [expression(i) for i in old_list if filter(i)]`

 is the same thing as:
 ```
 new_list = []
for i in old_list:
    if filter(i):
        new_list.append(expressions(i))
```
with syntax:

 `[ expression for item in list if conditional ]`

Simple print:
 ```
 x = [i for i in range(10)]
print x

# This will give the output:
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
Multiply:
```
list1 = [3,4,5]
 
multiplied = [item*3 for item in list1] 
 
print multiplied 
[9,12,15]
```
** See also examples of `first letter in each word`, `upper/lower case converter`, `print numbers only from a string`, `parsing a file`