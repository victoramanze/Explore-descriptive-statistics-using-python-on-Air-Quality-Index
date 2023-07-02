# Explore-descriptive-statistics-using-python-on-Air-Quality-Index
As an analyst you are tasked to analyze the data on air pollutions with respect to carbon mono-oxide . After the last analysis on finding the state with high level pollution in need of Oxygen support now some stakeholders wants better understanding of the dataset and you need to analyze it to make it easier so even a 5 years old could understand .

This will be a series of projects on statistical skills using python so i will be posting on statistical python for my next few projects and all are beginners friendly for those trying to get into data science this can be a great start on your journey and also those loving Linear regression and Machine learning.

first we start by importing relevant libraries and functions for analysis

import pandas as pd
import numpy as np
now we load the dataset into the dataframe . the dataset provided is in a csv format named C4 epa air dataset which contains subsets of data from the Enviromental Protection Agency

epa_data = pd.read_csv("c4 epa air dataset.csv", index_col = 0)
Now we explore the data

To understand how the dataset is structured, display the first 10 rows of the data.


let us recall that the aqi column represents the EPA’S Air quality index and are measured in parts per millions , per the unit of measure column

Now we get a descriptive stat using the describe function

epa_data.describe()

Now we notice that count value for the aqi column s 260 . That means there are 260 aqi measurements represented in the dataset

Now let us make sure we take note of the 25th percentile

Noticing that the 25th percentile is 2. This means that 25% of the aqi values in the data are below 2 parts per million.

What about the 75th percentile which is 9 .This means that 75% of the aqi values in the data are below 9 parts per million

now we start taking the statistical test we start by getting some descriptive statistics about the states in the data

epa_data["state_name"].describe()

Note:
Sometimes you have to individually calculate statistics. To review to that approach, use the numpy library to calculate each of the main statistics in the above table for the aqi column.

There are 260 state values, and 52 of them are unique. California is the most commonly occurring state in the data, with a frequency of 66. (In other words, 66 entries in the data correspond to aqi measurements taken in California.)

Now let us look into the result and evaluate this analysis first we compute the mean value from the aqi column

np.mean(epa_data["aqi"])

This is an important measure as it tells you what the average air quality is based on the data.

The mean value for the aqi column is approximately 6.76 (rounding to 2 decimal places here). This means that the average aqi from the data is approximately 6.76 parts per million.

Next we compute the median value from the aqi column

np.median(epa_data["aqi"])

This is also an important measure for understanding the central location of the data.

The median value for the aqi column is 5.0. This means that half of the aqi values in the data are below 5 parts per million.

Next,
identify the minimum value from the aqi column.

np.min(epa_data["aqi"])

This is also a very important measure also, as it tell you the best air quality observed in the data.

The minimum value for the aqi column is 0. This means that the smallest aqi value in the data is 0 parts per million.

Now,
identify the maximum value from the aqi column.

np.max(epa_data["aqi"])

The maximum value for the aqi column is 50. This means that the largest aqi value in the data is 50 parts per million.

Now,
compute the standard deviation for the aqi column.

By default, the numpy library uses 0 as the Delta Degrees of Freedom, while pandas library uses 1. To get the same value for standard deviation using either library, specify the ddof parameter to 1 when calculating standard deviation below.

np.std(epa_data["aqi"], ddof=1)

The standard deviation for the aqi column is approximately 7.05 (rounding to 2 decimal places here). This is a measure of how spread out the aqi values are in the data.

Considerations
Functions in the pandas and numpy libraries can be used to find statistics that describe a dataset. The describe() function from pandas generates a table of descriptive statistics about numerical or categorical columns. The mean(), median(), min(), max(), and std() functions from numpy are useful for finding individual statistics about numerical data.

This is how you present your findings to stakeholders
First you consider the most relevant points noted as you respond.

. “AQI values at or below 100 are generally thought of as satisfactory. When AQI values are above 100, air quality is considered to be unhealthy — at first for certain sensitive groups of people, then for everyone as AQI values increase.”

. “An AQI of 100 for carbon monoxide corresponds to a level of 9 parts per million.”

. The average AQI value in the data is approximately 6.76 parts per million, which is considered safe with respect to carbon monoxide. FUrther, 75% of the AQI values are below 9 parts per million, which is the standard for healthy air quality levels in terms of carbon monoxide.

. Regarding AQI values above 9 parts per million (indicating unhealthy levels of carbon monoxide), an effective presentation would include materials identifying which regions have worse air quality. It would also advise the appropriate team to conduct further research in those regions in order to understand this issue and improve the conditions in those regions. In order to conduct further analysis at a state-level, it would be helpful to collect more data from other states.

summary to stakeholders
75% of the AQI values in the data are below 9 parts per million, which is the standard for healthy air quality levels in terms of carbon monoxide.
Funding should be allocated for further investigation of the regions with unhealthy levels of carbon monoxide in order to learn how to improve the conditions.
Data Scientist. Data Analyst. Data storyteller. Data Enthusiast
