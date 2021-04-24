## Pythonisms

Read [dunder methods](https://dbader.org/blog/python-dunder-methods)

Read [iterators](https://dbader.org/blog/python-iterators)

Read [Generators](https://dbader.org/blog/python-generators)

## Dunder

Dunder (aka Special, Magic) methods let you emulate the behavior of built-in types. `__init__`

This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

You can see Python’s data model as a powerful API you can interface with by implementing one or more dunder methods. If you want to write more Pythonic code, knowing how and when to use dunder methods is an important step.

## Iterators

I love how beautiful and clear Python’s syntax is compared to many other programming languages.

Let’s take the humble for-in loop, for example. It speaks for Python’s beauty that you can read a Pythonic loop like this as if it was an English sentence:

```
numbers = [1, 2, 3]
for n in numbers:
    print(n)

```

## Generators

Class-based iterator method:  This is where Python’s generators enter the scene. If I rewrite this iterator class as a generator, it looks like this:

```
def repeater(value):
    while True:
        yield value

```

And that’s quite a fitting mental model for what happens here. You see, when a return statement is invoked inside a function, it permanently passes control back to the caller of the function. When a yield is invoked, it also passes control back to the caller of the function—but it only does so temporarily.

Whereas a return statement disposes of a function’s local state, a yield statement suspends the function and retains its local state.

In practical terms, this means local variables and the execution state of the generator function are only stashed away temporarily and not thrown out completely.

Execution can be resumed at any time by calling next() on the generator:

```
>>> iterator = repeater('Hi')
>>> next(iterator)
'Hi'
>>> next(iterator)
'Hi'
>>> next(iterator)
'Hi'
```