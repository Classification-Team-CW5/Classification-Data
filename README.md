# Classification-Data
# Data Description
Data The collection of this data was funded by a Canada Foundation for Innovation JELF Grant to Chris Bauch, University of Waterloo. The dataset aggregates tweets pertaining to climate change collected between Apr 27, 2015 and Feb 21, 2018. In total, 43943 tweets were collected. Each tweet is labelled as one of the following classes:

# Class Description
* 2 News: the tweet links to factual news about climate change
* 1 Pro: the tweet supports the belief of man-made climate change
* 0 Neutral: the tweet neither supports nor refutes the belief of man-made climate change
* -1 Anti: the tweet does not believe in man-made climate change

# Variable definitions
- sentiment: Sentiment of tweet
- message: Tweet body
- tweetid: Twitter unique id

# Files available for download
* train.csv - We will use this data to train your model.
* test_with_no_labels.csv - We will use this data to test your model.
* resample.png - Picture diagram explaining kfold validation and bootstrapping. 
* imbalance.png - Picture depicting the balanced accurancy formula 

# Using the data

The data looks like this in github:

### Train Data

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/github%20view%20of%20data.jpg?raw=true" alt="Github train data" title="Github train data" width="150" height="100" /> 

### Test Data

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/github%20view%20of%20the%20test%20data%20.jpg?raw=true" alt="Github test data" title="Github test data" width="150" height="100" /> 

When you download the data and present it in excel it has the following representation:

### Train Data 

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/pandas%20view%20of%20the%20train%20data%20.jpg?raw=true" alt="Pandas train data" title="Pandas train data" width="150" height="100" /> 

### Test Data

<img src="https://github.com/Classification-Team-CW5/Classification-Data/blob/main/pictures%20of%20train%20set%20raw/pandas%20view%20of%20the%20test%20data%20.jpg?raw=true" alt="Pandas test data" title="Pandas test data" width="150" height="100" /> 

From the representation above we can see that this is not ideal for any of the data representation that we want to do and thus we import this data into our notebook found here using the following code :
```python:
# Load train and test datasets
train = pd.read_csv("https://raw.githubusercontent.com/Classification-Team-CW5/Classification-Data/main/train.csv")
test = pd.read_csv("https://raw.githubusercontent.com/Classification-Team-CW5/Classification-Data/main/test_with_no_labels.csv")

```
In the code above the test data has been saved as pandas dataframes with the variables `test` and `train` respectively 

This data can be seen using the `.head()` function on a pandas data frame which by default displays the first five rows of the data by default :

### Train Data 

### Test Data

Notice how due to the way the data has been imported an index has automatically been generated as highlighted in yellow on both the test and the train dataframes. 

>The `test` data has two columns and the `train` data has three columns the `sentiment` column being the one that is present in the train data and not in the test data 

# Quick Overview of the data 

The data above has the following properties:
