---
layout: post
title: Random Forest
description: So, you must have read one of our last blogs on decision trees in ML; here in this blog, we will talk about a much wider concept in terms of application as well as scope. Random Forest has been considered as the panacea of all the data science problems. On a lighter note, when one can’t think of any algorithm, use random forest (irrespective of the situation)!
date: 2020-10-27
featured: no
---

<img src="/blog/RF/rf.jpeg">

Random Forest is a versatile machine learning method capable of performing both the regression and classification tasks. It is a type of the ensemble learning method, in which a group of weak models combine to form a powerful model.

It can be properly defined as <b> a classifier that contains a number of decision trees on various subsets of the given dataset and takes the average to improve the predictive accuracy of that dataset. </b>
Instead of relying on one decision tree, the random forest takes the prediction from each tree and based on the majority votes of predictions, and it predicts the final output.

<b> The Algorithm of Random Forest </b>
Random forest is like the bootstrapping algorithm with Decision tree (CART) model. Let’s say, we have 1000 observations in the complete population with 10 variables. Random forest tries to build multiple CART (decision tree) models with different samples and different initial variables. For instance, it would take a random sample of 100 observations and 5 randomly chosen initial variables to build a CART model. It will repeat the process, say 10 times, and then make a final prediction on each observation. The final prediction is the function of each prediction. This final prediction can simply be the mean of each of the predictions.

<img src="/blog/RF/1_each of the predictions.png">
<b> The Working Process of Random Forest can be explained in the below steps- </b>
Step 1 - Firstly, select random K data points from the training set.
Step 2 - Now, build the decision trees associated with the selected data points (Subsets).
Step 3 - Choose the number N for the decision trees that you want to build.
Step 4 - Repeat Steps 1 & 2.
Step 5 - For new data points, find out the predictions of each decision tree, and assign the new data points to the category that wins the majority votes.
Random forest prediction pseudo-code-
To perform predictions; the trained random forest algorithm uses the below pseudo-code.

1. Take the test features and use the rules of each randomly created decision tree to predict the outcome and stores the predicted outcome (target)
2. Calculate number of votes for each predicted target.
3. Always consider the high voted predicted target as the final prediction from the random forest algorithm.
   Now, we do understand that, some of the words or terms used above must have gone above your head; that’s no problem at all; we will understand the concept with the help of a real life example as well as a case study.

Random Forest Algorithm; A Basic Real Life Example.
Suppose, Saksham wants to go to different places that he may like for his vacation, and he asks his friend for advice. His friend will ask which places he has been to already, and whether he likes the places that he’s visited. Based on Saksham’s answers, his friend starts to give the recommendation. Here, his friend forms the decision tree.
Saksham wants to ask more friends for advice because he thinks only one friend cannot help him make an accurate decision. So, his other friends also ask him some random questions, and finally, provide an answer. He will consider the place with the most votes as his vacation decision.
His friends asked him some questions and gave the recommendation of the best place based on the answers. The friends created the rules based on the answers and used the rules to find the answer that matched the rules. Saksham’s friends also randomly asked him different questions and gave answers, which for they are the votes for the place. At the end, the place with the highest votes is the one he will select to go. This is the typical Random Forest algorithm approach.
Now, we move on to a serious and intuitive case study to actually understand why the concept of Random Forest is so useful, and how it is used practically.

Case Study on Usage of Random Forest in ML
Following is the distribution of Annual income GINI Coefficients across different countries-

<img src="/blog/RF/2_Gini.png">

Mexico has a population of 118 Million. Let’s assume that, the algorithm Random forest picks up 10k observations with only one variable (for simplicity) to build each Decision tree (CART model). In total, we are looking at 5 CART models being built with different variables. In a real life problem, you will have more number of population samples and different combinations of input variables.
Salary bands-
Band 1 - Below $40,000
Band 2 - $40,000 – 150,000
Band 3 - More than \$150,000
Following are the outputs of the 5 different CART models.
CART (Decision Tree) 1- Variable Age
<img src="/blog/RF/3_Cart1.png">

CART 2 - Variable Gender
<img src="/blog/RF/4_Cart2.png">

CART 3 - Variable Education
<img src="/blog/RF/5_Cart3.png">

CART 4 - Variable Residence
<img src="/blog/RF/6_Cart4.png">

CART 5 - Variable Industry
<img src="/blog/RF/7_Cart_5.png">

Using these 5 Decision Tree models (CART models), we need to come up with single set of probability to belong to each of the salary classes. For simplicity, we will just take the mean of probabilities in this case study. Other than simple mean, we will also consider the vote method to come up with the final prediction. To come up with the final prediction let’s locate the following profile in each of the CART models-

1. Age- 35 years,
2. Gender- Male,
3. Highest Educational Qualification- Diploma holder,
4. Industry- Manufacturing,
5. Residence- Metro
   For each of these Decision tree (CART models), following is the distribution across salary bands-

<img src="/blog/RF/8_finalcart.png">

The final probability is simply the average of the probability in the same salary bands in different CART models. As we can see from this analysis, that there is 70% chance of the individual falling in class 1 (less than \$40,000) and around 24% chance of the individual falling in class 2.
Final Inference
Random forest gives much more accurate predictions when compared to simple Decision Tree (CART) or regression models in many scenarios. These cases generally have high number of predictive variables and huge sample size. This is because it captures the variance of several input variables at the same time and enables high number of observations to participate in the prediction.

So, we hope that you must have understood the concept of ‘Random Forest’ in Machine Learning through the blog. Do write your precious feedback, and feel free to ask any doubt related.
