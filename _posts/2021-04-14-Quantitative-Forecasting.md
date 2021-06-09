---
layout: post
title: Quantitative Forecasting
description: As the term Quantitative suggests, we rely on mathematical data or numbers to forecast.
date: 2021-04-14
featured: no
---

<img src="/blog/Quantitative_Forecasting/feature.png">

What is Forecasting?

Forecasting in analytics carries the same meaning as in the English language i.e., predicting values and outcomes. As the term Quantitative suggests, we rely on mathematical data or numbers to forecast. And exactly how do we do that? What methods do we use? That’s the focus of this blog.

Before delving any deeper, let's understand the importance of forecasting and why exactly do we need to understand the methods used for the same. Forecasting is valuable as it gives us the ability to make informed business decisions and develop data-driven strategies.

Forecasting quantitatively i.e., using data analysis to predict future trends, advances and changes helps us make calculated and prudent decisions. Most financial and operational decisions are made based on current market conditions and predictions on how the future looks, for which we naturally need to forecast. You can't predict uncertainties, but forecasting helps you to be proactive rather than reactive when faced with dire situations.

The models we use to forecast outcomes quantitatively can be broadly classified into two categories:

1. Associative models
   Associative models are where we identify and analyze a causal relationship between the given variables. For that we require Pattern. A pattern between the outcome and the factors is what enables us to understand the model and extend it to predict the results for other data values.

2. Time series models
   So, what do we mean by a time series? Let's just break it in simpler terms. It refers to any series that represents data in a chronological order. These models examine the past data patterns and predict the future outcomes based on underlying patterns which we identify in the given data.

ASSOCIATIVE MODELS

Linear Regression is perhaps the most famous tool used for the same at the basic level. It basically identifies the pattern and states it in the form of a linear equation. Another thing it calculates is the P-Value, which is nothing but the coefficient of correlation between the dependent and independent variables.

As an example, let’s see if we can use a student’s reading capability to predict his acumen in mathematics. (Refer to the first 150 data entries in the dataset available at https://www.kaggle.com/spscientist/students-performance-in-exams).

First, we calculate the correlation (Multiple R) between reading score and the maths score, which comes out to be 0.867. This gives us the R-Squared as 0.751.

What R-Squared tells us is that how much of the variation seen in y-variable can be explained by the given x-variable. In this case, it is 0.751 i.e., around 75% of the variation in maths score can be explained by the variation in Reading score. Now this does not mean that the change is x-variable causes the change in y-variable. This has to do with the fact that correlation does not necessarily mean causality.

R-Squared as 0.751 is significant, which means that variables are linearly related to each other and the data is a good fit for linear regression. This can be visually seen in the following graph as the data points seem to neatly arrange themselves in a straight line (linear manner).

<img src="/blog/Quantitative_Forecasting/3.png">

Now that we have established that the relationship exists, let’s analyze the linear equation received through the regression analysis. This is the equation of the line of the best fit (see the previous graph):

<img src="/blog/Quantitative_Forecasting/2.png">

This means that an increase of 10 marks in reading score leads to an increase of around 9 marks in the math score. How do we interpret this? Logically, reading and mathematics are two polar opposite skills with seemingly no connection to each other. One possible explanation is that there might be a third factor (such as Parental Education level) which enables these students to be good at both the skills. This leaves the data open to further analysis.

One last factor we must take into account is the confidence we should have in the given results. It could be possible that the relationship we observed between the values was merely a coincidence. What is the chance that if we were to take some random values instead of the given dataset, we would get the same (or even stronger) relationship?

For that we turn to p-value. For the time being, we need not concern ourselves with its calculation. In this case the p-value is 1.42E-46, which is nearly zero. It means, that there is nearly 0% chance that we will be able to replicate the results by taking some random values. So, we can be confident of the relationship established by the regression analysis. Traditionally speaking, a p-value of less than 0.05 is a good indicator that the result established is not just a mere coincidence.

In Statistical Lingo, we have something called a Null Hypothesis, which generally means that result obtained is not special and is just a fluke. p-value is the evidence in the favour of Null Hypothesis. So higher the p-value, the less evidence we have in favour of the Null Hypothesis, and more confidence we have in the analysis.

But what if the data arranged itself into a shape other than a straight line? That’s when we turn to other more advanced forms of regressions viz: Polynomial Regression, Logistic Regression, among others. But again, this is a story for another time.

TIME SERIES MODELS

Perhaps the most famous example for a data set in this category is the stock price. A good way to predict the future prices is to analyze past trends.

For that, first, we must account for extreme short-term fluctuations by making the curve smoother to focus on the long-term trends. Moving Average does the same, as can be seen in the following chart.

<img src="/blog/Quantitative_Forecasting/1.png">

In Moving Average, each data entry is equated to the average of previous N entries, where N is a natural number whose magnitude depends upon the level of smoothness required.

Once we have the smooth curve, we can then use other more complex and advanced analytic tools to predict the prices. We have various types of time series models and methods to choose from based on the intended future like trend projections, simple mean, and exponential smoothing among many.

But once again, that is a story for another time...
