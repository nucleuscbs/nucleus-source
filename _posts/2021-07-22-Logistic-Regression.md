---
layout: post
title: Logistic Regression And Surviving The Titanic
description: Logistic Regression is the go to method for binary classification in machine learning. In the article, we'll be learning about the logit function, and using it to solve the one of the most popular problems on Kaggle, the Titanic Dataset.
date: 2021-07-22
featured: no
---

Logistic Regression, or the Logit Model, is one of the fundamental blocks of statistics and machine learning. It is used when the dependent variable is categorical, and is the go to method for binary classification (two class values). For example, the probability of win/lose or pass/fail an exam. Most popular use of logistic regression today is in determining if an email is spam or not.

<img src="/blog/LogisticRegression/Logistic1.jpg">

<h1>How does it work?</h1>
At the core of the logistic regression is the logit function, also called the sigmoid function and was developed by statisticians to describe properties of population growth in ecology, biology and environment sciences. It’s an S-shaped curve that maps any real-valued number into a value between 0 and 1, not necessary at only those limits. The equation for Logistic Regression is:

<img src="/blog/LogisticRegression/Logistic2.jpg">

Where y is the predicted output, B0 is the intercept and B1 is the coefficient for (x). It can be said that Logistic regression is a linear function. However, the predictions are morphed into classification using the logit function.
Example of Logistic Regression

We can use an example to learn Logistic Regression better. Let’s say we have data that can be used to predict a person’s gender based on their height. Given a height of 150cm is the person male or female.

Let’s say that the coefficients are b0 = -100 and b1 = 0.6. The above equation can be utilized to predict if a person is male given a height of 150cm or more formally P(male|height=150).
<b>y = e^(b0 + b1*x) / (1 + e^(b0 + b1*x))</b>
<b>y = e^(-100 + 0.6*150) / (1 + e^(-100 + 0.6*x))</b>
<b>y = 0.00004539</b>

The probability is so low that it can be used as 0, and certainly this person is not male.
Since, this is classification and we want a crisp answer, we can create bins for a complete classification of the values, for example:

<b>0 if p(male) < 0.5</b>
<b>1 if p(male) >= 0.5</b>

Logistic regression models are models that have a certain fixed number of parameters that depend on the number of input features, and they output categorical predictions, like for example if a cancer is malignant or not. 

<h1>Types of Logistic Regression</h1>

<b>Binary Logistic Regression:</b> The final response has only two possible outcomes. For example, either a student passes an exam or not.

<b>Multinomial Logistic Regression:</b> More than two possible outcomes, without any ordering. For example, predicting which of the election candidates wins among many.

<b>Ordinal Logistic Regression:</b> An ordered possibility of outcomes. For example, figuring out the movie rating from 1 to 5.

However, in this article we’ll be focusing solely on the binary classification type as it is the most popular among the three. '

<h1>Surviving a Disaster and The Titanic Dataset</h1>

The most popular dataset on Kaggle, undoubtedly, is the Titanic Dataset. It can also be considered a rite of passage for aspiring data scientists learning classification models. And why not, the data is structured in a way that helps people learn the fundamentals of classification and logistic regression.

<img src="/blog/LogisticRegression/Logistic3.png">

The dataset has the following variables (attributes) which are explained very well on Kaggle.

<img src="/blog/LogisticRegression/Logistic4.png">

Here, we shall use the train.csv provided to train the model and predict the survival of a passenger based on the given variables.

<h1>Code </h1>

<h3>Importing the dataset, and understanding the data: </h3>

import pandas as pd
titanic = pd.read_csv("train.csv")
titanic.shape

<img src="/blog/LogisticRegression/Logistic5.png">
<img src="/blog/LogisticRegression/Logistic6.png">
<img src="/blog/LogisticRegression/Logistic7.png">

<h3>Data Preprocessing </h3>

It is also worth noting that ‘Embarked’ has 3 classes C, Q, S which have to be converted into individual attributes.

<img src="/blog/LogisticRegression/Logistic8.png">

Here, we’ve used the ‘get_dummies’ function to create separate variables for each Embarked class. And we’ve joined the new dataframe with the original dataframe.

We’ve created two dataframes X and y, which will be used for Logistic Regression and learning. And dropped multiple non-numeric attributes which have no effect on the survival of a passenger. 

<img src="/blog/LogisticRegression/Logistic9.png">

We see that ‘Age’ has many null values, so we use ‘mean’ to impute null values.

<img src="/blog/LogisticRegression/Logistic10.png">

<h3>Creating the Model</h3>

We’ll use ScikitLearn to create the Logistic Regression model, and split the dataset into 80% (used for training the model) and 20% (for testing the model).

<img src="/blog/LogisticRegression/Logistic11.png">

After the model is created, it is necessary to check how well it has performed. The model score for testing is 0.754, which means that 75.4% of the time the model correctly predicts if a passenger has survived the disaster or not. We also figured out the intercept and coefficients (the array is made up of all the attributes used in the model).

<img src="/blog/LogisticRegression/Logistic12.png">

However, the correlation between the attributes and survival can be better understood with a visual.

<img src="/blog/LogisticRegression/Logistic13.png">

This cell’s output is a heatmap that shows the correlation between all the attributes.
<img src="/blog/LogisticRegression/Logistic14.jpg">

<h1>Conclusion</h1>
Logistic regression is one of the most exciting concepts in statistics and a powerful tool to classify data. However, one shortcoming of Logit functions is that they are not able to work well with outliers and leads to overfitting. Hence, we must try and remove outliers from the data provided to make the model more accurate. 

This was the most simple method that can be used to train a ML Logistic model. We can always use more sophisticated models for better prediction and classification using a more detailed analysis of the data and more complex feature engineering.
