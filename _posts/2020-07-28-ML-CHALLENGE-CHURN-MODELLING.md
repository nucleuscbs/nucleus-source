---
layout: post
title: ML CHALLENGE - CHURN MODELLING
description: Sometime back we started with our Voyage-à-Machine-Learning series to provide an opportunity for everyone to know all about Machine Learning and its applications. It culminated with a small challenge involving the use of various techniques covered in the series.

date: 2020-07-28
featured: yes
---
![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/ML CHALLENGE – CHURN MODEL.jpg)
The topics covered in the series were,

All about Machine Learning
Random Forest
Logistic Regression
K-Nearest Neighbours
Support Vector Machines (SVMs)
Clustering
Association rule learning with Apriori
Deep Learning and AI
To provide hands on practice so that our followers can now learn while practicing we opened a Machine Learning Challenge based on Churn Modelling. An important area of operation of banks is Churn Analysis. Churn Modelling or Analysis is the evaluation of the customer loss rate in order to reduce it. Banks are intrigued to identify segments of such customer as the cost for associating with a new customer is usually higher than retaining the old one.

For this challenge, a dataset was provided wherein, a Bank is witnessing some unusual churn rates and thus they want to predict whether a customer will leave the bank or not, based on the data provided.

The winner of the Challenge, Soham Mukherjee, majorly performed following 4 steps to solve this Challenge-

1. Exploratory Data Analysis

2. Data Pre-Processing

3. Data Modelling

4. Boosting Techniques

Exploratory Data Analysis (EDA)
Imagine your friends decide to go out for dinner to a restaurant you have never heard of before. Being a foodie, you will straight away find yourself perplexed with several questions. As a rule of thumb, you would go online to check for menu, reviews, and ratings. Furthermore, you will dig out details on the experience of people from the restaurant. 

Whatever research you will undertake before finally booking your table for the dinner is nothing but what Data Scientists in their language call “Exploratory Data Analysis”

EDA refers to the analytical procedure of performing preliminary investigations on data in order to discover patterns, to detect abnormalities in data, to test hypothesis and to check assumptions with the support of insights on synopsis and graphical representations of data provided.

In this case, our Winner performed multiple EDA techniques including checking for skewness, visualizing with help of histogram plots, and checking the relationship between variables. Further distribution of dependent variable was depicted using a pie chart. 

Data is always first available in human readable form due to which the data is labelled with words. However, Label Encoding is applied to convert the words into numeric values and make the data in machine-readable form. Therefore, the categorical variables (Geography, Gender) were first encoded with the help of following code-
![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/Winner_s Python code/1.png)

Once data was verified for duplications, the participant checked the skewness of the variables and then further illustrated the frequency-variable chart for each variable as shown below-
![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/Winner_s Python code/2.png)

Then, some detailed visualizations were prepared with help of Pair Plots. One of the most significant analysis is to check the relationship between the two variables. To accomplish that so that further decisions could be made, a heat map was plotted that illustrating the correlation between the variables-
![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/Winner_s Python code/3.png)

Since Correlation of X with itself is always 1, we get a diagonal which divides data into two triangles.

Now that Exploratory Data Analysis has been performed and required results fetched, by going into the intricacies of data with help of certain visualizations, the next step would be Data Pre-processing to make data fit for Machine Learning Modelling.

Data Pre-processing
This stage is one of the most significant steps in Machine Learning and no data scientist can ever skip this step in his/her analysis. 

To define in simple words, Data Preprocessing is a technique to convert the raw data which has been gathered from numerous sources into cleaner and more meaningful pieces of information. Datasets are incredibly massive and usually contain unnecessary data as well. That vast amount of information is also heterogeneous by nature, which means that they don’t share the same structure and thus there is also a need to standardize the data first. Data Preprocessing technically deals with issues such as inconsistent data, missing values, insufficient data, imbalance data, etc.

In the winner’s entry, special attention was given to this step and he removed the “Balance” variable as it would decrease accuracy. It was observed from the correlation matrix between all the variables that Balance variable can reduce the accuracy of model as it was less related to the target and other variables.  Further to handle the imbalance and inconsistent data following two techniques were performed-

SMOTE for Handling Imbalanced Data- 
Data imbalance usually reflects an unequal distribution of classes within a dataset and a major issue associated is that there are very few examples of the minority class in data for a model to effectively learn and predict. Therefore, to overcome this issue, one way is to oversample the examples in the minority class. The same can be achieved by replicating examples from the minority class in the training dataset before fitting a model. This can balance the class distribution without providing any additional information to the model. An improvement over replicating examples from the minority class is to synthesize new examples from the minority class.

For the same, the most widely used approach to synthesizing new examples is called the Synthetic Minority Oversampling Technique (SMOTE). SMOTE first selects a minority class instance at random and finds its k-nearest minority class neighbours. These synthetic training records are generated by randomly selecting one or more of the k-nearest neighbours for each example in the minority class. After the oversampling process, the data is reconstructed and several classification models can be applied for the processed data.
![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/Winner_s Python code/4.png)

Standardization of Inconsistent Data-
The purpose of standardising the dataset is to ensure that each of the variables contributes equally to the analysis without any bias. It becomes essential to do standardization before applying Machine Learning Models as variables are the core of the model and the analysis is pretty much sensitive regarding the variance of initial variables. That is if there are variables with large differences between the initial variables, the variable with larger range will dominate over the smaller ranges. 

For example, consider two variables, distance within city and distance between cities. One of the variables is measured in meters while the other in Kilometres. Now if the data is not standardised then distance of 500 meters would be considered as greater than distance of 5KM, which isn’t true. Therefore, transforming the data to comparable scales can prevent this problem. 

Mathematically, it is done by subtracting the mean and dividing by the standard deviation for each value of each variable.

z = (value – mean)/ (standard deviation)

All the variables will be transformed to the same scale once the standardization is completed. Finally, the data is divided into training and test sets for further steps.

Data Modelling
This is a technique to analyse data and acquiring certain results from it. There are various data modelling techniques which can be used such as Random Forest Regression, Logistic Regression, K Nearest Neighbours etc. All these techniques can be used to fit in the dataset and then predict the required outcome. For this purpose, dataset is divided into two categories-

Train set- For fitting the model.
Test set- To predict the required outcome.
The various data modelling techniques used in this case are-

Logistic Regression
Random Forest Classifier
Decision Tree Classifier
Support Vector Machines
K nearest neighbours
Here is the code and confusion matrix for the Random Forest Classifier;

![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/Winner_s Python code/5.png)
Heatmap from the seaborn library has been used in the Confusion Matrix for better understanding-

The confusion matrix shows that among all positive predictions, 84.4% of the predictions were true positives and it was correctly predicted that a customer will churn. Rest 15.6% were false positives which means that it was wrongly predicted that these customers will churn.

Similarly, out of the negative predictions, 83.8% were true negatives while rest 16.2% were false negatives and they were wrongly predicted.
![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/Winner_s Python code/6.png)

Boosting Techniques-
Boosting techniques helps to convert weak learners into strong learners. The various boosting techniques used in the case are-

Gradient Boosting Classifier
Ada boost Classifier
XG Boost
Here is a sample code for Gradient Boosting Classifier
![ML Challenge](/blog/2020-07-28-ML CHALLENGE - CHURN MODEL/Winner_s Python code/7.png)

The winner has used certain techniques to increase the accuracy of the model in the XG Boost technique-

Random search has been used to find out the best parameters with the help of a Param grid. It searches among a given set of values to find out parameters with highest accuracy.
Stratified-K-Fold shuffles the data and then split the dataset into n-splits (specified number of splits) Then it uses each part as a test set.
When applying machine learning models, one usually does data pre-processing (as explained above), feature engineering, feature extraction and, feature selection. After this, he/ she selects the best algorithm and tuning of the parameters is done in order to obtain the best results.

AutoML is a series of concepts and techniques used to automate these processes. It reduces the bias and errors that occur when a human being is designing the machine learning models. An organization can also reduce the cost of hiring many experts by applying AutoML in their data pipeline. The winner achieved the best accuracy with the help of Stacked Ensemble (Auto ML).

We hope that you understood the framework used in order to solve this Challenge. Also, if the training time of model was increased from 5 minutes to probably a couple of hours, the model, the accuracy would have been around a remarkable 94-96%. In case of any queries, feel free to reach out to us.

