## Python Decorators

notes from [this article](https://realpython.com/primer-on-python-decorators/)


Functions: return a value based on given arguments

Functions are `First-Class Objects`:
meaning they can be passed around and used as arguments like other objects

`Inner Functions`: 
- Define functions inside of other functions 
- The order of inner functions is determined when they are called/executed, not necessarily the order in which the code appears in the function block.
- Not defined until the parent function is called (and it calls/executes the inner function)

- Locally scoped to the parent inside the parent function as `local variables`

- Without () you are returning a `reference` to the inner function

- Decorators wrap a function, modifying its behavior
```
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_whee():
    print("Whee!")
```
`@mydecorator` applies the decorator to say_whee() function

You can reuse decorators by importing them:
`from <decorators file> import <name>`

You cannot decorate a function that takes an argument, so use *args and *kwargs in the inner wrapper function to make them accept any number of arguments and pass them on to the function it decorates

see [this](https://realpython.com/python-kwargs-and-args/) on *args and *kwargs
```
def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        func(*args, **kwargs)
    return wrapper_do_twice
```

Your decorators can mess with return values of the function it decorates--MAKE SURE the wrapper function returns the intended value of the decorated function
```
def do_twice(func):
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        return func(*args, **kwargs)
    return wrapper_do_twice
```
Introspection is the ability of an object to know about its own runtime and attributes set

Try using `@functools.wraps` decorator to preserve info about the original function 
(need to `import functools`)

You can stack and apply several decorators to the same function; executed in the order they are listed

You can pass arguments to your decorators:
`@repeat(num_times=4)`

Inner functions can have decorators

When a decorator uses arguments, you need to add and extra outer function OR make the function optional
`def name(_func=None, *, kw1=val1, kw2=val2, ...):` the *indicates following params are keyword-only

[keyword-only article](https://www.python.org/dev/peps/pep-3102/)



See the article for `@timer` decorator to return the time it takes a function to execute, @debug, and @slow_down, @register examples

**Check out [Flask-Login extension](https://flask-login.readthedocs.io/en/latest/#flask_login.login_required)


You can also use class as a decorator but to be callable, it must contain an `__init__()`and `__call__()` where call is executed every time you call an instance of the class

```
class Counter:
    def __init__(self, start=0):
        self.count = start

    def __call__(self):
        self.count += 1
        print(f"Current count is {self.count}")
```
Singletons:
- a class with only one instance (None, True, False, etc)
- in Python it's better to use a global variable vs a Singleton

** See the example of Fibonacci caching using a function to create a lookup table in recursive function

** Check out more info on [@register for Plugins](https://realpython.com/primer-on-python-decorators/#registering-plugins)

** See example of using JSON



>>Note: The @timer decorator is great if you just want to get an idea about the runtime of your functions. If you want to do more precise measurements of code, you should instead consider the timeit module in the standard library. It temporarily disables garbage collection and runs multiple trials to strip out noise from quick function calls.



>>Note: In functional programming, you work (almost) only with pure functions without side effects. While not a purely functional language, Python supports many of the functional programming concepts, including functions as first-class objects.

>>Note: In the beginning of this guide, we talked about pure functions returning a value based on given arguments. Stateful decorators are quite the opposite, where the return value will depend on the current state, as well as the given arguments.