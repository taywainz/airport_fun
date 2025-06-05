# airport_fun
`python` `numpy` `pandas`\
</br>
This repository contains ways you can analyze Kaggle's provided airports dataset. Specifically, this goes over how to clean your data and analyze flight arrival or departure delays.\
To download this dataset, click [here](https://www.kaggle.com/usdot/flight-delays/download).

## Data manipulation and cleaning
### Why data manipulation is important
Data manipulation is the process of cleaning and organizing data into a readable format.
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

### Explore the data
Exploring data will allow you to recognize the unstructured and unorganized data. There are many different methods people use to first explore a dataset. Below are some of the best, quickest way to do so:
* `head()` - column names and first few rows of data are outputted
* `info()` - summary of the dataframe including column names, non-null count, and datatype (dtype)
* `describe()` - mathematical statistics of the _numeric_ data including count, mean, standard deviation (std), min, 25%, 50%, 75%, and max
* `shape` - number of rows and columns

### Missing data
Missing data is very common in dataframes. To easily identify missing data, `info()` can be used to find the _non-null_ count per column, or `isnull().sum()` to output the _null_ count per column.</br>
</br>
Missing data can skew the statistics of your data. Below are some options on how to handle missing data in a dataframe:
* `dropna()` - by default, it drops any row that contains at least 1 null value
  * `dropna(axis=1)` to drop any _column_ that contains a null value. Can also specify a sparticular column name
* `fillna()` - fills null values with a specified value
* `SimpleImputer` - replaces null values in each column using a descriptive statistic like mean, median, or most frequent
  * This class is heavily used in machine learning since it can impute values on the training set, validation set, and test set.</br>
</br>

We are interested in looking at flight delays for flights based on the time of year, airline, or origin / destination airport. The following steps are taken to clean the necessary columns:
*  Create a copy of the original `flights` dataset
*  Select columns of interest
*  Drop rows where "DEPATURE_DELAY" and "ARRIVAL_DELAY" are null
> ```python
> flight_delays = flights.copy()
>
> ## viewing columns
> flight_delays.info()
> 
> ## selecting columns
> flight_delays = flight_delays[['YEAR','MONTH','AIRLINE','ORIGIN_AIRPORT','DESTINATION_AIRPORT','DEPARTURE_DELAY','ARRIVAL_DELAY']]
>
> ## dropping rows
> flight_delays = flight_delays.dropna(subset=['DEPARTURE_DELAY','ARRIVAL_DELAY'])
> ```

> [!CAUTION]
> Always make a copy of your dataframe! This is good practice in case you make an incorrect manipulation. If you do not make a copy, any change made will affect the original dataframe.

## Flight Delays
We have already cleaned our dataframe, but now we will analyze these delays.\
To be continued...
