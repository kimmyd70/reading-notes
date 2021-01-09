## Python Dunder Methods

notes from [this article](https://dbader.org/blog/python-dunder-methods)

dunder = short for double under(line)

Also called special or magic methods

Let you emulate the behavior of built-in types

Example: length of string
```
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```
Example: slicing

implement a `__getitem__` method which allows you to use Python’s list slicing syntax: `obj[start:stop]`

**Check out [Python Data Model](https://docs.python.org/3/reference/datamodel.html)

*** Object Representation

`__repr__`: The “official” string representation of an object. This is how you would make an object of the class. The goal of `__repr__` is to be unambiguous.

`__str__`: The “informal” or nicely printable string representation of an object. This is for the end user.

** Iteration

```def __reversed__(self):
    return self[::-1]

def __len__(self):
        return len(self._transactions)

    def __getitem__(self, position):
        return self._transactions[position]
```
** Comparison

```
def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance < other.balance
```
** Look under dir() builtin to see all dunders

Since Python treats everything as an object, you can concatonate 2 of the same type





