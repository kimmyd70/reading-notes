![XKCD comic about recursion](./images/xkcd-recursion.png)

## Recursion

notes on [this article](https://www.geeksforgeeks.org/recursion/)

- A process where a function calls itself directly or indirectly

- The function that calls itself is the **recursive function**

- Factorial is a simple example

- Need to include the base case for each (all) recursive functions to avoid stack overflow

```
int fact(int n)
{
    if (n < = 1) // base case
        return 1;
    else    
        return n*fact(n-1);    
}
```
- **Indirect Recursion**

"A function fun is called indirect recursive if it calls another function say fun_new and fun_new calls fun directly or indirectly."

- A **Tail Recursive** function is a function with the recursive call as the last thing executed by the function

From the author on **memory allocation**

"When any function is called from main(), the memory is allocated to it on the stack. A recursive function calls itself, the memory for a called function is allocated on top of memory allocated to calling function and different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues."


- Recursive and iterative approaches can both be written for a problem

    - recursive has greater space (all functions remain in the stack) and time requirements

    - recursive is a clean and simple way to code (but may become less readable)



![Nesting dolls recursion](./images/nesting-dolls.jpg)