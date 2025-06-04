# Data manipulation and cleaning
`python` `numpy` `pandas`
## Why data manipulation is important
Data manupulation is the process of cleaning and organizing data into a readable format.
Since the majority of raw data you will run into in the real-world is unstructured, data manipulation is _crucial_.</br>
</br>
Before data manipulation can begin, the necessary libraries were imported and data from the csvs were loaded.
> ```python
> import pandas as pd
> import numpy as np
>
> airlines = pd.read_csv('airlines.csv')
> airports = pd.read_csv('airports.csv')
> flights = pd.read_csv('flights.csv')
> ```

## Explore the data
Exploring data will allow you to recognize the unstructured and unorganized data. There are many different methods people use to first explore a dataset. Below are some of the best, quickest way to do so:
* `head()` - column names and first few rows of data are outputted
* `info()` - summary of the dataframe including column names, non-null count, and datatype (dtype)
* `describe()` - mathematical statistics of the _numeric_ data including count, mean, standard deviation (std), min, 25%, 50%, 75%, and max
* `shape` - number of rows and columns

## Missing data
Missing data is very common in dataframes. To easily identify missing data, `info()` can be used to find the _non-null_ count per column, or `isnull().sum()` to output the _null_ count per column.</br>
</br>
Missing data can skew the statistics of your data. Below are some options on how to handle missing data in a dataframe:
* `dropna()` - least preferred method. By default, it drops any row that contains at least 1 null value.
  * `dropna(axis=1)` to drop any _column_ that contains a null value

> [!CAUTION]
> Before making any data manipulation, make a copy of the original dataframe! A copy allows you to manipulate the dataframe without changing the original dataframe. To make a copy, create a new variable and pass it `df.copy()`.

