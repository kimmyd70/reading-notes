## Call Stack

+ A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function, etc.

    - When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.

    - Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.

    - When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.

    - If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.

+ The call stack is primarily used for function invocation (call). Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.

+ In Asynchronous JavaScript, we have a callback function, an event loop, and a task queue. The callback function is acted upon by the call stack during execution after the call back function has been pushed to the stack by the event loop.

+ At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

+ **Temporarily store:** When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

+ **Manage function invocation (call):** The call stack maintains a record of the position of each stack frame. It knows the next function to be executed (and will remove it after execution). This is what makes code execution in JavaScript synchronous.

+ A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

+ Error messages can be:
    - Reference (undeclared var)
    - Syntax (causes parsing error)
    - Range (such as ref outside array length)
    - Data Type (mismatch)

+ Consider console.log, adding break points, or try/catch, linters, quokka to avoid and debug