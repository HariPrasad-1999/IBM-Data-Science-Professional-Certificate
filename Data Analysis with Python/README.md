# Data Analysis with Python

## <u>1)Python Packages for Data Science</u>

A Python library is a collection of functions and methods that allow you to perform lots of actions without writing any code. 
The libraries usually contain built in modules providing different functionalities which you can use directly and there are extensive libraries offering a broad range of facilities. 
We have divided the Python data analysis libraries into three groups. 


#### Scientific Computing Libraries
  
  1) <b>Pandas</b> = Pandas offers data structure and tools for effective data manipulation and analysis. It provides facts, access to structured data. The primary instrument of Pandas is the two dimensional table consisting of column and row labels, which are called a data frame. It is designed to provid easy indexing functionality. 
  2) <b>Numpy</b> = The NumPy library uses arrays for its inputs and outputs. It can be extended to objects for matrices and with minor coding changes, developers can perform fast array processing.
  3) <b>SciPy</b>= This Library includes functions for some advanced math problems as listed on this slide, as well as data visualization.
 
#### Visualization Libraries (These libraries enable you to create graphs, charts and maps.)
  
  1) <b>Matplot</b> = Matplotlib package is the most well known library for data visualization. It is great for making graphs and plots. The graphs are also highly customizable.
  2) <b>Seaborn</b> = It is based on Matplotlib. It's very easy to generate various plots such as heat maps, time series and violin plots.

#### Algorithmic Libraries
  
  1) <b>Scikit-Learn</b> = the Scikit-learn library contains tools statistical modeling, including regression, classification, clustering, and so on. This library is built on NumPy, SciPy and Matplotib. 
  2) <b>Statsmodel</b> = Statsmodels is also a Python module that allows users to explore data, estimate statistical models and perform statistical tests. 

## <u>2)Understanding the Problem & Data</u>

<img src="https://miro.medium.com/max/1200/1*YPsZO50dIiEKpW9RqzqsTw.jpeg">


## <u>3)Importing & Exporting Data in Python</u>
Once we have our data in Python, then we can perform all the subsequent data analysis procedures we need.
To read any data using Python's pandas package, there are two important factors to consider,
* Format = Format is the way data is encoded. We can usually tell different encoding schemes by looking at the ending of the file name.
  * Some common encodings are: CSV, JSON, XLSX, HDF and so forth. 
* File Path = The path tells us where the data is stored. Usually, it is stored either on the, 
  * Computer = "C:/ThisPC/Users/Desktop/data.csv"
  * Internet = "https://archive.ics.uci.edu/autps/imports-85.data"


#### Importing CSV without Header
The data format is CSV, which stands for comma separated values. At this point, these are just numbers and don't mean much to humans, but once we read in this data we can try to make more sense out of it. In pandas, the read_CSV method can read in files with columns separated by commas into a pandas data frame. Reading data in pandas can be done quickly in three lines.

```
import pandas as pd
# read the online file by the URL provided above, and assign it to variable "df"
path="https://archive.ics.uci.edu/ml/machine-learning-database/autos/imports-85.data"

df = read_csv(path,header=None)
```

#### Printing the dataframe in Python
* `df` prints the entire dataset(not recommended for large datasets)
* `df.head(n)` to show the first <i>n</i> rows of dataframe.
* `df.tail(n)` to show the bottom <i>n</i> rows of dataframe.



#### Adding headers
It is difficult to work with the data frame without having meaningful column names. However, we can assign column names in pandas.
We first put the column names in a list called headers, 
`headers=["Name of Headers","are written","In quotes"]`
then we set `df.columns=headers` to replace the default integer headers by the list. 
If we use the head method introduced in the last slide to check the dataset, we see the correct headers inserted at the top of each column.
`df.head()` to see the output.

#### Exporting Pandas dataframe to CSV
Using the method to_CSV, we can convert dataframe into CSV format. To do this, specify the file path which includes the file name that you want to write to. For example, if you would like to save dataframe on computer, use the syntax df.to_CSV.

The Exporting formats are:-<br>
<img src="https://github.com/HariPrasad-1999/IBM-Data-Science-Professional-Certificate/blob/ad1166ff35754186760366e0fbe35dba0a4c19e8/Data%20Analysis%20with%20Python/pics/THEJ-AWS.PNG">

## <u>4)Analyzing the Dataset</u>
 Analyzing is shown in .ipnb file - "Review Introduction".
 Download the file to view.
 
 
## <u>5)Pre-Processing the Data</u>
The process of converting or mapping data from one raw form into another format to make it ready for further analysis. Data preprocessing is often called Data cleaning or Data wrangling.
* What to do to encounter the missing values in data?
   
Ans - When no data value is stored for feature for a particular observation, we say this feature has a missing value.
* How to deal with Missing Data?

  Ans - Usually missing value in data set appears as question mark and a zero or just a blank cell.There are many ways to deal with missing values and this is regardless of Python, R or whatever tool you use. Of course, each situation is different and should be judged differently.<br>
  * Check with the data collection source.
    <p>The first is to check if the person or group that collected the data can go back and find what the actual value should be.</p>
  * Drop the missing values
    * Drop the variable - Drop particular rows.
    * Drop the data entry - Drop particular column.
  * Replace the missing values 
    * Replacing it with an average(of similar datapoints).
      <p>As an example, suppose we have some entries that have missing values for the normalized losses column and the column average for entries with data is 4500. While there is no way for us to get an accurate guess of what the missing value is under the normalized losses column should have been, you can approximate their values using the average value of the column 4500.</p> 
    * Replacing it by Frequency(Mostly for Categorical and non integer data)
    * Replace it based on other functions.
    * Leave it as missing data.
