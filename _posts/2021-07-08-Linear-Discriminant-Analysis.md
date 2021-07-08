---
layout: post
title: Linear Discriminant Analysis
description: Linear Discriminant Analysis is a dimensionality reduction technique used as a preprocessing step in Machine Learning and pattern classification applications.
date: 2021-07-08
featured: no
---

Imagine the world is struck by a devastating pandemic (even need to imagine?). The pandemic is taking the lives of people across the world and has put the world to a halt. People are eagerly waiting for a vaccine and scientists are working hard to make one. Now, making a vaccine isn’t an easy business - after doing a lot of research you find that different people react differently to the vaccine and a vaccine might have severe after-effects on a small group of people depending upon several differentiating factors among the people. How to classify these different people which have a specific effect after taking the vaccine based on a much fewer number of factors? That is, how to reduce the number of variables differentiating these people without losing information provided by other variables? 

<h2>INTRODUCTION</h2> 

Linear Discriminant Analysis is what we call a dimensionality reduction technique. Given all the factors that you have and all the information they contain, you try to squeeze that information into as few dimensions or variables as you can. 
Take a multiple regression model with 5 variables as an example. The model squeezes all the info in the factors into a single variable, i.e. the predicted y-value. It is an example of dimensionality reduction as it reduces multiple factors into a single variable without losing any substantial information.
Linear Discriminant Analysis does something very similar, but with a different objective. In regression, we are concerned with predicting the dependent variable with as much accuracy as possible. Whereas, LDA reduces the dimensions in such a way that it becomes easy to classify the dependent variable. In rough terms, it tries to predict a categorical dependent variable.
And it is this very feature of LDA, that makes it indispensable for the vaccine problem discussed in the beginning. But how exactly does LDA reduce the dimensions? Let’s find out.

<h2>INTUITION</h2>

Let’s start with a basic example having two independent variables X1 and X2. Using these two variables, we want to predict if the dot will be red or blue.

<img src="/blog/Linear-Discriminant-Analysis/1.jpg">

One way to reduce dimensions, in this case, is to project the values on either of the axes, i.e., you reduce the dimension by completely ignoring one of them. Needless to say, this is not an efficient way as we lose substantial amounts of data in the process. So, what we do is create a new axis using both the variables available to us and project the values onto that.

<img src="/blog/Linear-Discriminant-Analysis/2.jpg">

It can be clearly seen that it is now relatively easier to predict the color of the dots. Roughly speaking, those values in the lower half of the line are blue and other red. But how do we form this axis? In regression models, we form the axis (line of best fit) using the ordinary least squares method. Let’s see how the same is achieved in LDA.

<h2>FORMULA</h2>

1.) The required line is the one that maximizes the following amount.

Here, μ represents the mean of the values in the respective categories (in our case, arithmetic mean for red and blue dots) and s squared represents the respective variations.

<img src="/blog/Linear-Discriminant-Analysis/3.jpeg">
<p style="text-align:center; font-size:18px;">via StatQuest</p>

2.) So basically, we try to separate the classes by maximizing the square of the distance between the means, and we try to improve the accuracy of the model by minimizing the “scatter” within individual categories.
One thing to keep in mind is that this is a basic formula where we only have two categories and two dimensions, to begin with. For more dimensions and categories, the formulas start expanding and become more complicated. But that is a story for another time...

<h2>CONCLUSION</h2>

Hope you got to know something about Linear Discriminant Analysis. It helps one separate different classes of objects, things, people, etc. based on their differentiators by reducing them. This can also be done by Principal Component Analysis covered by us <a href="https://theanalyticsbay.com/blog/Principal-Component-Analysis/" style="color:#a0f1ff"><u>here</u></a>, but Linear Discriminant Analysis focuses on maximum separability of the objects to be classified and hence is more accurate.
