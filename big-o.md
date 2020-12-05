![Big O graph](./images/big-o-pic.png)

Notes on [this article](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/)

Big O notation is used to describe the computational complexity of an algorithm in A) execution time or B) storage space needed

**O(1)** 

describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

**O(N)** 

describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. 

in loops, Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

**O(N<sup>2</sup>)** 

represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N<sup>3</sup>) , O(N<sup>4</sup>) etc.

**O(2<sup>N</sup>)** 

denotes an algorithm whose growth doubles with each additon to the input data set. The growth curve of an O(2N) function is exponential - starting off very shallow, then rising meteorically. An example of an O(2N) function is the recursive calculation of Fibonacci numbers.

**O(log N)** 

as in the binary search, O(log N)produces a growth curve that peaks at the beginning and slowly flattens out as the size of the data sets increase (ie: a logarithmic curve)