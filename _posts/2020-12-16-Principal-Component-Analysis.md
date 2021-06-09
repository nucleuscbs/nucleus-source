---
layout: post
title: Principal Component Analysis
description: When someone discovers that you are writing a research paper, one of the many questions asked is “Why are you writing on this particular topic?”. The question seems fairly easy to answer. You are writing a research paper because you are not entirely satisfied with the available reading on that particular topic. The same logic has been applied here. Principal Component Analysis is an important technique to understand in the field of statistics and data science but the resources available for it were too technical to comprehend. Therefore, we’ll have a look at What, Why and How part concerning PCA to further grasp the topic
date: 2020-12-16
featured: no
---

<img src="/blog/pca/1.png">
Let’s say we want to predict the impact of COVID-19 on Stock Markets and General Business Activities for different countries. For this we have tons of information like the opening and closing price, lowest and highest price, correlation of different indices over the world, inflation rate, unemployment rate, days of lockdown, cases reported, and so on… This sort of problem has an overwhelming number of variables, and someone who has worked earlier with a lot of variables knows what all obstructions this may present. The question is, “How do we take all of the variables collected and focus on only few of them?” In terms of Analytics, we simply want to “Reduce the Dimension Space.” By Dimensionality Reduction, we have fewer variable relationship to consider which makes data easy to explore and visualize to get the desired outcomes.

Principal Component Analysis is nothing but a Dimensionality Reduction technique to reduce the feature space of large data-sets with numerous variables by transforming a large data-set into a smaller one but still with maximum information so to make analysing data much easier and quicker for machine learning algorithms and tuning techniques without unrelated variables to process. PCA helps in Noise Filtering, Visualization, Feature Extraction, Stock Market Predictions, Gene Data Analysis and many more. Another fascination property of PCA is that it is both a technique of Feature Extraction as well as a medium to perform Feature Extraction, as it combines the input variables in such a way that it drops the extraneous variables while keeping the more important ones.
Now since What, Why and When parts have been answered, let’s move to the most important question, that is How?

<b> HOW DOES PCA WORK? </b>

Let’s look at the step by step how Principal Component Analysis works-

<b> 1. STANDARDIZATION </b>

The purpose of standardising the dataset is to ensure that each of the variable contributes equally to the analysis without any bias. It becomes essential to do standardization before PCA as variables are the core of the PCA and the analysis is pretty much sensitive regarding the variance of initial variables. That is if there are variables with large differences between the initial variables, the variable with larger range will dominate over the smaller ranges.
For example, consider two variables, Distance within city and distance between cities. One of the variables is measured in meters while other in Kilometers. Now if the data is not standardised than distance of 500 meters would be considered as greater than distance of 5KM, which isn’t true. Therefore, transforming the data to comparable scales can prevent this problem. Mathematically, it is done by subtracting the mean and dividing by the standard deviation for each value of each variable.
<i> z = value – mean/(standard deviation) </i>

All the variables will be transformed to the same scale once the standardization is completed.

<b> 2. COVARIENCE MATRIX COMPUTATION </b>

<img src="/blog/pca/2.png">

Often variables are correlated in such a way that they contain redundant information. Thus, to understand the relationship between the variables and identify such correlations, we compute the covariance matrix. The covariance matrix is an n×n symmetric matrix, where n is the number of dimensions. For example, for a 5-dimensional data set with 4 variables a, b, c, d and e, the covariance matrix is a 5×5 matrix of the from-

Since covariance of a Variable with itself is nothing but its variance [Cov(a,a) = V(a)] therefore the diagonal elements in the covariance matrix are the variance of each variable.

<b> 3. COMPUTING THE EIGENVECTORS AND EIGENVALUES OF THE COVARIANCE MATRIX </b>

Eigenvectors and eigenvalues are the linear algebra concepts that we are required to process from the covariance matrix to decide the "principal components" of the data. Principal components are the new variables that are constructed as a result of combinations done in a manner that the new components are uncorrelated and most of the information within the initial variables are compressed into the first components. For example, there is 10-dimensional data that provides 10 principal components, but PCA tries to put maximum possible information in the first component, then maximum remaining information in the second and so on as shown in the plot below-

<img src="/blog/pca/3.png">

Computing the eigenvectors and eigenvalues to organising the principal components in this manner helps if dimensionalty reduction without losing much information. Statistically, Principal Components represent the direction of data that explains the maximum amount of variance.

<b> 4. FEATURE VECTOR </b>

Feature Vector is the first visible step of dimensionality reduction with help of Principal Component Analysis. It is a a matrix of the columns of those eigenvectors that we decide to keep say k, where k < n, that is k is always less than the n, which was the number of initial Eigenvectors. The decision of selection is based on the eigenvalues, i.e. components with lesser significance are discared.

For Example, suppose we create a feature vector by discarding one of the eigenvector as it was carrying only 2% information and therefore even though dimension now becomes k=n-1, we still have the necessary 98% of information carried by the other eigenvectors.

<b> 5. LAST STEP - RECAST THE DATA ALONG THE PRINCIPAL COMPONENTS AXES </b>

In all the previous steps, excluding Standardisation, we didn’t make any change with the data and just selected the principal components and form the feature vector. The purpose of this step is to use the feature vector and reorient the data from the axis of the original variables (n axis) to the ones represented by the principal components, k axis (hence, the name Principal Components Analysis)

This can be achieved by multiplying the transpose of the original data set by the transpose of the feature vector which we formed with the help of principal components.

<b> FinalData = Feature_VectorT \* Standardized_Original_Data </b>

Here’s an example from setosa.io where we transform 5 data points using PCA-

<img src="/blog/pca/4.png">

So, we hope that you must have understood the concept of this not so explored technique in data science and statistics as we answered the final question of how PCA works. Hit the like button, if you liked our post; and subscribe our blog to be connected to us, as many more wonderful topics are underway -)
