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

This is where Python’s generators enter the scene. If I rewrite this iterator class as a generator, it looks like this:

```
def repeater(value):
    while True:
        yield value

```

