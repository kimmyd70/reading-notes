## Fixtures and Coverage
### Testing with pytest
notes from [this article](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)

### *** Fixtures ***
You'll want to have some objects available to all of your tests. Those objects might contain data you want to share across tests, or they might involve the network or filesystem. These are often known as "fixtures" in the testing world, and they take a variety of different forms.

define a fixture using the decorator `@pytest.fixture` around your function

1.  Works similiar to if you were to define your function as a global variable
2. At the same time, fixtures are used differently from global variables. For example, let's say you want to include this fixture in one of your tests. You then can mention it in the test's parameter list. Then, inside the test, you can access the fixture by name. For example:

```
def test_reverse_lines(simple_file):
   assert reverse_lines(simple_file) == ['cba\n', 'fed\n',
 ↪'ihg\n', 'lkj\n']
 ```

 3. Your fixture might act like data, in that you don't invoke it with parentheses. But it's actually a function under the hood, which means it executes every time you invoke a test using that fixture. This means that the fixture, in contrast with regular-old data, can make calculations and decisions.

 4. Adding `@pytest.fixture(scope='module')` the scope parameter controls how many times your fixture runs.  `module` means be it will available throughout your tests but will execute only a single time.  No parameter means the fixture will run once per test in your suite.


*** see also "Testing Your Code with Python's pytest" [Part I](https://www.linuxjournal.com/content/testing-your-code-pythons-pytest) and [Part II](https://www.linuxjournal.com/content/testing-your-code-pythons-pytest-part-ii)

### *** Coverage ***

1. When software gets larger and more complex, it's not going to be so easy to eyeball it. That where you want to have "code coverage", checking that your tests have run all of the code.

2. Now, 100% code coverage doesn't mean that your code is perfect or that it lacks bugs. But it does give you a greater degree of confidence in the code and the fact that it has been run at least once.

3. So, how can you include code coverage with pytest? It turns out that there's a package called pytest-cov on PyPI that you can download and install. Once that's done, you can invoke pytest with the --cov option. If you don't say anything more than that, you'll get a coverage report for every part of the Python library that your program used, so I strongly suggest you provide an argument to --cov, specifying which program(s) you want to test. And, you should indicate the directory into which the report should be written. So in this case, you would say: `pytest --cov=mymul .`

4. Turn your coverage report into human readable with `coverage html` which produces a directory called `htmlcov` and check out `index.html` for a readable report

check out: Brian Okken's Python testing with pytest, published by Pragmatic Programmers. He also has many other resources, about pytest and code testing in general, at [Brian's Blog](http://pythontesting.net).

