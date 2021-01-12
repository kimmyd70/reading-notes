## Python Random Module

notes from [this article](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python) and [this additional reading](https://docs.python.org/3/library/random.html)

>>[THIS ARTICLE](https://realpython.com/python-random/) is important explanation of Python pseudo-random and explains why Game of Greed (usually) generates the same roll on the first roll.  In GoG we use the default seed with a very limited sample set (1-6) so there are fewer permutations for a 6-die roll

This module implements pseudo-random number generators for various distributions.

It generates a random float uniformly in the semi-open range [0.0, 1.0)

### ** Randint
If we wanted a random integer, we can use the randint function Randint accepts two parameters: a lowest and a highest number. Generate integers between 1,5. The first value should be less than the second.

Return a random integer N such that `a <= N <= b`. 

Alias for `randrange(a, b+1)`.

```
import random
print random.randint(0, 5)
```
This will output either 1, 2, 3, 4 or 5.

### ** Random
If you want a larger number, you can multiply it.
For example, a random number between 0 and 100:

```
import random
random.random() * 100
```
### ** Choice
Generate a random value from the sequence sequence.
```
random.choice( ['red', 'black', 'green'] )
```
The choice function can often be used for choosing a random element from a list.
```
import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)
```
### ** Shuffle
The shuffle function, shuffles the elements in list in place, so they are in a random order.

```from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)
```
Output:
print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
of course your results will vary

`random.shuffle(x[, random])`
shuffles the sequence x in place.

The optional argument `random` is a 0-argument function returning a random float in [0.0, 1.0); by default, this is the function `random()`.

To shuffle an immutable sequence and return a new shuffled list, use `sample(x, k=len(x))` instead.

The optional argument will be removed in v 3.11.  Depreciated wtih 3.9

### ** Randrange
Generate a randomly selected element from range(start, stop, step).  

Changed in version 3.2: `randrange()` is more sophisticated about producing equally distributed values. 
```
random.randrange(start, stop[, step])
import random
for i in range(3):
    print random.randrange(0, 101, 5)
```
### ** Flip a coin code example
```
import random
import itertools

outcomes = { 'heads':0,
             'tails':0,
             }
sides = outcomes.keys()

for i in range(10000):
    outcomes[ random.choice(sides) ] += 1

print 'Heads:', outcomes['heads']
print 'Tails:', outcomes['tails']
```
There are only two outcomes allowed, so rather than use numbers and convert them, the words “heads” and “tails” are used with choice().

The results are tabulated in a dictionary using the outcome names as keys.


### ** Choices (statistical implications)
`random.choices(population, weights=None, *, cum_weights=None, k=1)`
Return a k sized list of elements chosen from the population with replacement. If the population is empty, raises `IndexError`.

If a weights sequence is specified, selections are made according to the relative weights. Alternatively, if a cum_weights sequence is given, the selections are made according to the cumulative weights (perhaps computed using itertools.accumulate()). For example, the relative weights [10, 5, 30, 5] are equivalent to the cumulative weights [10, 15, 45, 50]. Internally, the relative weights are converted to cumulative weights before making selections, so supplying the cumulative weights saves work.

If neither weights nor cum_weights are specified, selections are made with equal probability. If a weights sequence is supplied, it must be the same length as the population sequence. It is a TypeError to specify both weights and cum_weights.

The weights or cum_weights can use any numeric type that interoperates with the float values returned by random() (that includes integers, floats, and fractions but excludes decimals). Behavior is undefined if any weight is negative. A ValueError is raised if all weights are zero.

For a given seed, the choices() function with equal weighting typically produces a different sequence than repeated calls to choice(). The algorithm used by choices() uses floating point arithmetic for internal consistency and speed. The algorithm used by choice() defaults to integer arithmetic with repeated selections to avoid small biases from round-off error.

Changed in version 3.9: Raises a `ValueError` if all weights are zero.

### ** Sample
`random.sample(population, k, *, counts=None)`
returns a k length list of unique elements chosen from the population sequence or set. Used for random sampling without replacement.

If the population contains repeats, then each occurrence is a possible selection in the sample.

Repeated elements can be specified one at a time or with the optional keyword-only counts parameter. For example, `sample(['red', 'blue'], counts=[4, 2], k=5)` 

is equivalent to 

`sample(['red', 'red', 'red', 'red', 'blue', 'blue'], k=5)`.

To choose a sample from a range of integers, use a `range()` object as an argument. This is especially fast and space efficient for sampling from a large population: sample(range(10000000), k=60).

If the sample size is larger than the population size, a `ValueError` is raised.

Changed in version 3.9: Added the counts parameter.

Deprecated since version 3.9: In the future, the population must be a sequence. Instances of set are no longer supported. The set must first be converted to a list or tuple, preferably in a deterministic order so that the sample is reproducible.
### ** Real-Valued Distributions for Statistical Analysis 
** (see second article) **

The following functions generate specific real-valued distributions. Function parameters are named after the corresponding variables in the distribution’s equation, as used in common mathematical practice:

    - random.random()
    - random.uniform(a, b)
    - random.normalvariate(mu, sigma)
    - random.gauss(mu, sigma)
    - random.weibullvariate(alpha, beta)
    - random.paretovariate(alpha)
    - random.triangular(low, high, mode)
    - random.betavariate(alpha, beta)
    - random.expovariate(lambd)
    - random.gammavariate(alpha, beta)
    - random.vonmisesvariate(mu, kappa)

### ** Warning:   
>The pseudo-random generators of this module should not be used for security purposes. For security or cryptographic uses, see the secrets module.

### ** Note:
>The default random() returns multiples of 2⁻⁵³ in the range 0.0 ≤ x < 1.0. All such numbers are evenly spaced and are exactly representable as Python floats. However, many other representable floats in that interval are not possible selections. For example, 0.05954861408025609 isn’t an integer multiple of 2⁻⁵³ 
(See the second article for an alternate recipe with mantissa)