---
layout: post
title: Autocorrelation
description: Autocorrelation, the word itself is suggestive of its very nature, signifying a mathematical representation of relationship between the same time series in its original form and as it’s lagged form.
date: 2020-12-02
featured: no
---

Autocorrelation shows the degree of similarity between a given time series and a lagged version of itself over successive time intervals. Lagged version of time series is simply the past period values of the concerned variable. This seemingly simple concept has wide application in fields of mathematics, statistics, and sciences. It is used in measuring optical spectra, short duration light pulses, in GPS system, portfolio and return optimization and much more. Unit root processes, trend-stationary processes, autoregressive processes, and moving average processes are specific forms of processes with autocorrelation.  
The resulting values ranges between -1 to 1, like the traditional correlation statistic. An autocorrelation of +1 represents a perfect positive correlation (an increase seen in one time series leads to a proportionate increase in the other time series). An autocorrelation of negative 1, on the other hand, represents perfect negative correlation (an increase seen in one time series results in a proportionate decrease in the other time series). But it must be remembered as words of caution that autocorrelation measures linear relationships. So even if the autocorrelation is minuscule, there may still be a nonlinear relationship between a time series and a lagged version of itself.

<b> Reasons of autocorrelation </b>
Some major reasons of autocorrelation include-

1. Carryover of effect- Carry over effect of variables in data causes autocorrelation. For ex- Data on monthly expenditure of a family in a particular city, preceding month expenditure will influence the expenditure of next month. This is called carry over effect.
2. Mis-specification of form of relationship in a model also causes autocorrelation. For ex- a study assumes that explanatory and study variables have linear relationship but they have logarithmic or exponential relation.
3. Measurement error- Errors may creep in due to difference between observed and true value of variable, data collection issues etc.

<b> Problems caused by autocorrelation </b>

1. Inefficient (but unbiased) ordinary least square estimate which fails to achieve smallest variance and any forecast based on them is hence inefficient. Efficient estimator gives most information about a sample and inefficient estimator may perform well but requires larger sample sizes to do so.
2. Exaggerated goodness of fit for a time series with positive serial correlation and an independent variable that grows over time.
3. Leads to overly optimistic view of R2.
4. Large variance in predictions based on the model and narrow confidence interval. The T statistics and F value are often not reliable.
5. It increases the occurrence of false negative for significant regression coefficient. Regression coefficients appear significant when they are not.

<b> Graphical approach through MS-Excel </b>

<img src="/blog/Autocorrelation/1.png">

Plotting the data with its lag clearly shows us there exist a relationship between the two, because the plot denotes a nearly definite pattern. This high relation is also denoted with correlation coefficient of 0.83.

But things are not always this simple. Such high value of correlation of a data with its past values would have made everything so predictable and easy eliminating the need of complex statistical analysis and modeling. Let’s take another example-

<img src="/blog/Autocorrelation/2.png">

The plot shows data points paired with their lagged values are scattered without any pattern or direction. This is again confirmed with a low correlation coefficient.

<b> Example 3 </b>- For finding autocorrelation of a series with different lags on excel we simply create a table with suitable lags and find the correlation using CORREL() function. We can plot the various correlations so obtain to have a better picture of the case.

<img src="/blog/Autocorrelation/3.png">

<b> Autocorrelation in R </b>
Finding autocorrelation is not always that simple because we test it with many lags. Repeating the same process with huge data sets becomes a tedious task in MS-Excel. Not to worry, we are again there for your rescue. Let’s try it out on R.
Documentation-
acf(x, lag.max = NULL,
type = c("correlation", "covariance", "partial"),
plot = TRUE, na.action = na.fail, demean = TRUE, ...)

x<- Time series data
lag.max<- Number of lags upta which correlation needs to be calculated
type<- Character string giving the type of acf to be computed. Allowed values are"correlation" (the default), "covariance" or "partial"
plot<- True or False based on whether you want plot or not

<b> What can you do? </b>

Removing autocorrelation involves making changing to the data, improvising the model and other tests and modifications. In layman language, for positive serial correlation one can add lags of dependent or independent variable in the model. For negative serial correlation one must check that none of the variables in over-differenced and for seasonal correlation one can add seasonal dummy variable to the model. It itself is a wide concept and we will surely cover it in detail in one of our subsequent blogs.

<b> Example </b>

Mr. X is a trader. While monitoring stock of ABD ltd he realized that usually whenever stock price rallies on Monday it is followed by decrease in price by the next day and a increase in price on Wednesday. Amused to know this, he tries to prove his observations quantitatively. He takes the daily returns of the share price and run autocorrelation on it with lag 1 to lag 10. He finds that returns one day prior have a negative autocorrelation of -0.74, while the returns two days prior have a positive autocorrelation of +0.83. Past returns seem to influence future returns. Therefore, Mr.X can adjust his position to take advantage of the autocorrelation and resulting momentum by selling the share the next day after a rally and buy them on the following day again. While doing this he never forgets that the chances of error remains high because what was right yesterday may prove wrong tomorrow and he continuously monitors other factors that govern the stock price while repeatedly checking the relevance of auto-correlation at appropriate intervals.

<b> Conclusion </b>

Autocorrelation is a wide concept. If discovered it can help us to detect patterns in our data, find seasonality and other interesting insights. If ignored it may distort our results. Just a basic awareness about its presence will help us improve our models and analysis. And I hope that we were successful in introducing and explaining the concept to you. Practice the methods we shared, explore new ones, and don’t forget to share your views and findings with us.
