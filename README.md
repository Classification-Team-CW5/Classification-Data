# Classification-Data

##  Table of contents
1. [Data Description](https://github.com/Classification-Team-CW5/Classification-Data#data-description)
2. []

## Data Description
Data The collection of this data was funded by a Canada Foundation for Innovation JELF Grant to Chris Bauch, University of Waterloo. The dataset aggregates tweets pertaining to climate change collected between Apr 27, 2015 and Feb 21, 2018. In total, 43943 tweets were collected. Each tweet is labelled as one of the following classes:

## Class Description
* 2 News: the tweet links to factual news about climate change
* 1 Pro: the tweet supports the belief of man-made climate change
* 0 Neutral: the tweet neither supports nor refutes the belief of man-made climate change
* -1 Anti: the tweet does not believe in man-made climate change

## Variable definitions
- sentiment: Sentiment of tweet
- message: Tweet body
- tweetid: Twitter unique id

## Files available for download
* [train.csv]() - We will use this data to train your model.
* [test_with_no_labels.csv]() - We will use this data to test your model.
* [resample.png]() - Picture diagram explaining kfold validation and bootstrapping. 
* [imbalance.png]() - Picture depicting the balanced accurancy formula 

## Using the data
There are many platforms that support importing this sort of data there are three listed below firstly we look at the data in its raw form "the way it is represented on github" and then we can also have a look at it in Microsoft Excel this will most likely be the default display of the data if it is downloaded from github. For our purposes with the data we are going to use it predominantly in a jupyter notebook in python. The goal of this text is to give you a better understanding of how the text is represented across the different systems and thus enable the reader to be able to replicate the notebook and/or make your own improvements.

### Github Raw
The data looks like this in github:

#### Train Data Github Raw

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/github%20view%20of%20data.jpg?raw=true" alt="Github train data" title="Github train data"  /> 

#### Test Data Github Raw

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/github%20view%20of%20the%20test%20data%20.jpg?raw=true" alt="Github test data" title="Github test data"  /> 

### MS Excel
When you download the data Microsoft Excel will most likely be the default app for opening the data on your device the pictures below show how these files will be represented by Microsoft Excel upon opening them using that app. 
>Please also note that there are a lot more rows in the files than the fourteen that are represented in the images below 

Excel it has the following representation:

#### Train Data MS Excel

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/Train%20excel.jpg?raw=true" alt="Excel train data" title="Excel train data"  /> 

#### Test Data MS Excel

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/Train%20excel.jpg?raw=true" alt="Excel test data" title="Excel test data" /> 

### Pandas Representation

We want to use this data in a way where we can make changes and alter it without changing the source data unlike in excel where the data is both stored locally and any saved change made alters the local source file. We would like to be able to call on the data and make our changes in the notebook there is no intent to save the data only the insights and predictions that can be made from it. For this we need to have on demand access to the data as multiple people will be working on one notebook from different machines and not make any alterations to the source file, thus pandas seems like the best choice for the task.

#### Setting up
 
 if pandas is not present on your jupyter notebook it can be installed with the following codes:
 ```python:
 # Install from PyPI
 pip install pandas
 ```
 
 ```python:
 #conda installation
 conda install pandas
 ```
You can read more about installing pandas [here](https://pandas.pydata.org/docs/getting_started/install.html).
 
 When you first startup your jupyter notebook please ensure that pandas is imported into your current notebook for importing pandas we use the following code:
 
 ```python:
 import pandas as pd
 ```
 in the code above we use the alias `pd` for pandas which is the standard in python coding.
 
We import this data into our juypiter notebook found here using the following code :
```python:
# Load train and test datasets
train = pd.read_csv("https://raw.githubusercontent.com/Classification-Team-CW5/Classification-Data/main/train.csv")
test = pd.read_csv("https://raw.githubusercontent.com/Classification-Team-CW5/Classification-Data/main/test_with_no_labels.csv")

```
In the code above the test data has been saved as pandas dataframes with the variables `test` and `train` respectively 

This data can be seen using the `.head()` function on a pandas data frame which by default displays the first five rows of the data by default :

#### Train Data in pandas

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/pandas%20view%20of%20the%20train%20data%20.jpg?raw=true" alt="Pandas train data" title="Pandas train data"  /> 

#### Test Data in pandas

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/pandas%20view%20of%20the%20test%20data%20.jpg?raw=true" alt="Pandas test data" title="Pandas test data" /> 

>Notice how due to the way the data has been imported an index has automatically been generated as highlighted in yellow on both the test and the train dataframes. 

The `test` data has two columns and the `train` data has three columns the `sentiment` column being the one that is present in the train data and not in the test data 

## Quick Overview of the data 

The data above has the following properties:

#### Train data:

- [The train data](https://raw.githubusercontent.com/Classification-Team-CW5/Classification-Data/main/train.csv) has three columns when imported in pandas namingly `sentiment`, `message` and `tweetid` please refer [here](https://github.com/Classification-Team-CW5/Classification-Data/blob/main/README.md#variable-definitions) for more detail on what these headings represent
-The train data consists of 15819 rows if working in pandas you can see this by using `.info()` function on the data 

#### Test data 
- [The test data](https://raw.githubusercontent.com/Classification-Team-CW5/Classification-Data/main/test_with_no_labels.csv) has two columns `message` and `tweetid` it does not contain a `sentiment` column as it is intended that you use the train data to make a model that will predict the `sentiment`
- The test data contains 10547 rows if working in pandas you can see this by using the `.info()` function on the data

[Back to the top](https://github.com/Classification-Team-CW5/Classification-Data#classification-data)
