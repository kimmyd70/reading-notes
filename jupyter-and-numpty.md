## Jupyter and NumPy

Notes from [this article](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)


### Jupyter
JupyterLab is a next-generation web-based user interface for Project Jupyter.

JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner. 

Documents and activities integrate with each other, enabling new workflows for interactive computing, for example:

1. Code Consoles provide transient scratchpads for running code interactively, with full support for rich output. A code console can be linked to a notebook kernel as a computation log from the notebook, for example.

2. Kernel-backed documents enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.

3. Notebook cell outputs can be mirrored into their own tab, side by side with the notebook, enabling simple dashboards with interactive controls backed by a kernel.

4. Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers. For example, it is easy to have live preview of Markdown, Delimiter-separated Values, or Vega/Vega-Lite documents.

JupyterLab also offers a unified model for viewing and handling data formats. JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.) and can also display rich kernel output in these formats. See [File and Output Formats](https://jupyterlab.readthedocs.io/en/stable/user/file_formats.html#file-and-output-formats) for more information.

** Checkout the article for links to keyboard shortcuts and maps, and extensions
_________
### NumPy

notes from [this article](https://www.dataquest.io/blog/numpy-tutorial-python/)

*** Checkout out [NumPy Arrays](https://www.tutorialspoint.com/numpy/index.htm)

**Data Analysis with Python**

A commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem,

The data is in what I’m going to call `ssv` (semicolon separated values) format — each record is separated by a semicolon (;), and rows are separated by a new line. 
```
"fixed acidity";"volatile acidity";"citric acid";"residual sugar";"chlorides";"free sulfur dioxide";"total sulfur dioxide";"density";"pH";"sulphates";"alcohol";"quality"

7.4;0.7;0;1.9;0.076;11;34;0.9978;3.51;0.56;9.4;5

7.8;0.88;0;2.6;0.098;25;67;0.9968;3.2;0.68;9.8;5
```
Work with the data using Python and the csv package. We can read in the file using the csv.reader object, which will allow us to read in and split up all the content from the ssv file.

*** Checkout how to import the data with `csv.reader`

*** Checkout how to create a NumPy 2-dim array

Or...

The below code will create an array with 3 rows and 4 columns, where every element is 0, using numpy.zeros:

```
import numpy as np
empty_array = np.zeros((3,4)) empty_array
```
It’s useful to create an array with all zero elements in cases when you need an array of fixed size, but don’t have any values for it yet.

Or...
using numpy.random.rand. Here’s an example:

`np.random.rand(3,4)` or as a vector slice `np.random.rand(3)`

`numpy.genfromtxt` reads in a text file

Access elements using `wines[2,3]` where the first row/column is [0,0]

Slice using `wines[0:3,3]` or `wines[:3,3]`

Select a column `wines[:,3]`

Assign values `wines[1,5] = 10`

or entire entire column `wines[:,10] = 50`

Slice a 2-dim to a 1-dim array: `third_wine = wines[3,:]` and access with a single index

These priinciples work with n-dim arrays

### Data Types

NumPy has several different data types, which mostly map to Python data types, like float, and str. You can find a full listing of NumPy data types here, but here are a few important ones:

1. float — numeric floating point data.
2. int — integer data.
3. string — character data.
4. object — Python objects.

Data types additionally end with a suffix that indicates how many bits of memory they take up. So int32 is a 32 bit integer data type, and float64 is a 64 bit float data type.

check using `wines.dtype`
reassign using `wines.astype(int)`

### Single Array Math

`wines[:,11] + 10`

array([ 15., 15., 15., ..., 16., 15., 16.])`


Note that the above operation won’t change the wines array — it will return a new 1-dimensional array where 10 has been added to each element in the quality column of wines.

If we instead did +=, we’d modify the array in place

Arrays must be the same size to do `element-wise math`

### Broadcasting

Unless the arrays that you’re operating on are the exact same size, it’s not possible to do elementwise operations. In cases like this, NumPy performs broadcasting to try to match up elements. Essentially, broadcasting involves a few steps:

The last dimension of each array is compared.

If the dimension lengths are equal, or one of the dimensions is of length 1, then we keep going.
If the dimension lengths aren’t equal, and none of the dimensions have length 1, then there’s an error.
Continue checking dimensions until the shortest array is out of dimensions.

### Array Methods
There are several other methods that behave like the sum method, including:

1. numpy.ndarray.mean — finds the mean of an array.
2. numpy.ndarray.std — finds the standard deviation of an array.
3. numpy.ndarray.min — finds the minimum value in an array.
4. numpy.ndarray.max — finds the maximum value in an array.

You can find a full list of array methods [here](https://numpy.org/doc/stable/reference/arrays.ndarray.html).

*** Subsetting,Comparisons, Reshaping, and Combining are all possible with intuitive operators

*** Cheat Sheet [here](https://s3.amazonaws.com/dq-blog-files/numpy-cheat-sheet.pdf)

