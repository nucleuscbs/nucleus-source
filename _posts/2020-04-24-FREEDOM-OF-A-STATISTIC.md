---
layout: post
title: FREEDOM OF A STATISTIC
description: Every human being needs a sense of freedom, some sort of independence in their lives. But did you know that the same is the case with statistics? Many measures in statistics are defined by their degree of freedom. Let’s find out what this term means.
date: 2020-04-24
featured: no
---
![Freedom of statistics](/blog/2020-04-24-FREEDOM-OF-A-STATISTIC/FREEDOM OF A STATISTIC.jpg)
Degrees of freedom, as the name suggests, refers to the number of variables in a data which are at freedom, that is they are independent of each other and can vary as they want to.

Think of it like this; there are 10 branches on a tree as well as 10 birds, who want to sit on those branches. The first bird has 10 branches to choose from, while the second bird has 9 branches to choose from, as the first bird has already sat down on one branch. Similarly, the last bird will have no choice, as when it arrives, birds will already be sitting on 9 out of 10 branches. Thus, only 9 out of 10 birds have the freedom to sit on the branch of their choice.

Now, consider this; we know the arithmetic mean of three unknown integers to be 8. If two of those three numbers are revealed to be 5 and 7, then the third number has to be 12, as per the formula of mean. So, in this case, the third number does not have any independence to vary and is dependent on the values of the first two numbers. Thus, in this case, degrees of freedom are 2 i.e. only two numbers out of three have the freedom to vary.

Now, another interesting question pops up: Why is (n-1) taken as the denominator to estimate sample variance rather than (n)?
Well, the same concept is used. (n-1) is used to correct the inherent bias in estimating the population variance, where n is the sample size. This removal of bias is done by multiplying the biased estimator by (n) and dividing by (n-1), and this rectifying process has a name: Bessel’s Correction.

Degrees of Freedom are not always (n-1), typically it varies based on the data, where it is being used, and the number of parameters we are estimating. For instance, in the simplest Linear Regression model, we estimate 2 parameters; the intercept and the slope. Hence, in this case, the degrees of freedom of the residuals will be (n-2).

We hope that you’ve understood the concept of degrees of freedom well with the explanation given above. Do mention your feedback using the comments section. For more similar posts, stay tuned!