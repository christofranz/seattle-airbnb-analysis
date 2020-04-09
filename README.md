
### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

You will need the standard data science libraries found in the Anaconda distribution of Python.  The code should run with no issues using Python versions 3.*.  


## Project Motivation<a name="motivation"></a>

For this project, I was interestested in analyzing data from AirBnB homes located in Seattle.  Specifically, I looked at the following questions:

1. How is the availability of the listings? Are AirBnB accomodations in Seattle available 365 years a day?
2. How much money can you earn as a host per month? And how is the monthly revenue of all hosts distributed?
3. What are the key drivers for the price of listings and is it possible to predict them?

To answer each question, I followed the CRISP-DM process including:

1) Business Understanding
2) Data Understanding
3) Data Preparation
4) Modeling
5) Evaluation
6) Deployment

### Business Understanding

In the first phase of the business understanding it is the goal to determine the goals and requirements of the data mining. The result of this are the three questions listed above. With the success of AirBnB also the number of protests increase and hence it is very valuable to get facts that support either the one or the other side.


### Data Understanding

Now an overview of the data is generated and tried to rate the quality of the data and any problems in regard of the planned goals from the step before. The AirBnB data from Seattle contains three different csv-files which are described in more detail in the [File Description](#files). The listings contain the field **availability_365** which gives information about how many days in the year the homes are available for renting. This can be directly used to answer the first question. Calculating the revenue per host and month is only possible with certain assumptions because the actual booked nights per listing are not contained. However, it is possible to approximate and estimate the corresponding revenues. For the last question the information from the listings are inspected regarding their meaning and importance for the price. But for sure they can be used to answer the last question to a certain extend.

### Data Preparation

Here a final data set for the modeling shall be generated. To reach this goal, the data needs to be inspected in more detail. Columns which are seldom filled can be neglected. On the other hands, columns with a rather small fraction of not filled values need to be kept. For numeric variables the mean value of each column is used to impute values. Categorical variables are replaced with dummy variables and all columns have to match the correct data type.


### Modeling

In this phase the for the defined task suiteable methods are applied on the prepared data set. The first two questions are answered by calculating certain statistics. For the last question both a linear regression and a random forest regression was implemented since it was a regression model. Linear regression is a very simple and fast approach to get first indications how easy the data can be fitted. Random Forst Regression is one of the best out of the box methods for supervised machine learning and hence used.


### Evaluation

The evaluation of the model and results can be found in the blog post mentioned in [Results](#results).


### Deployment

Finally, the preparation and visualization of the results is done. This can be found in the notebooks and the blog post.


## File Descriptions <a name="files"></a>

The following are the files available in this repository:

* `ListingsAvailability.ipynb` - a notebook of the analysis of the availability of the listings in Seattle

* `RevenueOfHosts.ipynb` - a notebook of the analysis of the monthly revenue of the hosts

* `PriceModeling.ipynb` - a notebook of the analysis of the key drivers of listing prices and the approaches to predict the price

* `calendar.csv` - this csv-file was not used for this particular analysis, but it was available from the original kaggle link

* `listings.csv` - csv containing the **id**, **description**, **host_id**, **price**, **availability_365** and many more information about each listing

* `reviews.csv` - csvs containing the **home_id**, **date** of review, **reviewer_id**, **reviewer_name**, and reviewer **comments** for the reviewed stays.

It is worth noting here that the reviews and calendar files did not have overlapping dates, and there were no numeric values associated with reviews.

## Results<a name="results"></a>

The main findings of the code can be found at the [blog post available here](https://TODO).

## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to AirBnB and Kaggle for the data.  You can find the Licensing for the data and other descriptive information for the [Seattle data on Kaggle](https://www.kaggle.com/airbnb/seattle).  
