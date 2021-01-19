## Pandas

notes from [this article](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)

Import pandas using the standard nomenclature `import pandas as pd` along with `import numpy as np`

Series input EX: `s = pd.Series([1,3,5])`and pandas will create default integer index 0:1, 1:3, 2:5

DataFrame: Pass in a dictionary and pd will convert to series-like object with keys as column headings and rows with integer index

    ** Unlike numpy arrays, df elements can be of different data types per COLUMN.  Use `df.dtypes` to view types
``` 
    df = pd.DataFrame(
        {
            key:value,
            key: value,
        }
    )
```   
    
Can create labeled columns with EX: `dates = pd.date_range("20130101", periods = 6)` to get a Date/Time Index of 6 days

Then create a DataFrame with custom row/column indices:
`df = pd.DataFrame(np.random.randn(6,4), index=dates, columns = list ("ABCD))`


Use `df.head` and `df.tail` to view first/last rows. `df.index` to see row headings and `df.columns` to see column headings

DataFrame.to_numpy() converts to a numpy array to see the underlying data, but cost of operation high if elements are of different data types.  Does not display indices or column headings

`df.describe()` displays data statistics including count, mean, std, min, 25%, 50%, 75%, max

`df.T` transposes row and column

`df.sort_index(axis = 1, ascending = False)` transposes columns

`df.sort_values(by = "column heading")` sorts that column in ascending and arranges indices to keep rows together

`df["column label"]` selects single column

`df[start index:end index]` selects rows (inclusively) as does `df["row label:"row label"]`

`df.loc[]` has many ways to slice by labels and multiple axes.   Always INCLUSIVE.  Get SCALAR  slicing by row and column label; often using row labels as an array (ie: dates[0]). Also `df.at[]` for SCALAR.

`df.iloc[]` slices by index/position with row/col arguments.  `df.iloc[int, int]` and `df.iat[int, int]` returns value by position

EX: `df[df["A"] > 0]` returns rows where BOOLEAN CONDITION is met

EX: `df2[df2["E"].isin(["two", "four"])]` filters rows of column E that meet the .isin criteria

SETTING: is done by adding a column, value by position, value by label, with numpy array or a ***where*** condition EX:`df2[df2 > 0] = -df2` (sets positive value to neg)

Uses NaN for missing data (`np.nan`); can be reindexed, dropped rows, fill values, or return boolean

Can perform stats on specific axis, operate on objects of different dimensionality.  Auto broadcasts along specified dimension and fills NaN as necessary

Other operations:
- apply functions
- generate histograms
- String methods like .lower
- Concatenate slices
- Join/ Merge columns
- `.groupby` for split based on criteria, perform function on group, recombine into df
- Stack and Unstack
- Pivot Tables
- Extensive Date/Time functionality and conversion
- Use Categoricals from the API docs
- Plotting and Visualization
- Read/Write to Excel
- Read/Write to HDF5 Store



More on [indexing and selecting](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#indexing) and [advanced indexing](https://pandas.pydata.org/pandas-docs/stable/user_guide/advanced.html#advanced)

More on [select by label](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#indexing-label)

More on [select by position](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#indexing-integer)

More on [missing data](https://pandas.pydata.org/pandas-docs/stable/user_guide/missing_data.html#missing-data)

More on [binary operations](https://pandas.pydata.org/pandas-docs/stable/user_guide/basics.html#basics-binop)

More on [Date/Time functionality](https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#timeseries)

More on [Plotting](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html#visualization)