---
layout: post
title: Decision Trees in Machine Learning
description: So, in the last blog, we introduced you to the world of Machine Learning; lets dive into a very important aspect of it, that is, ‘Decision Trees’. A tree has many analogies in real life, and it turns out that it has influenced a wide area of machine learning.
date: 2020-04-18
featured: no
---
![Decision Trees](/blog/2020-04-18-Decision-Trees/Decision Trees.jpg)
Let us first understand; what exactly a decision tree is & it’s working.

A decision tree is a type of supervised learning algorithm (having a predefined target variable) which is mostly used in classification problems. It works for both the categorical and continuous input and output variables. In this technique, we split the population or samples into two or more homogeneous sets (or sub-populations) based on most significant splitter/differentiator in input variables.

Okay, so all the definition stuff might scare you, so let’s understand this concept with the help of an example.

Let us say, we have a sample of 30 students with three variables Gender (Boy/ Girl), Class (IX/ X) and Height (5 to 6 ft). 15 out of these, 30 play cricket in free time. Now, we want to create a model to predict who will play cricket during a leisure period? In this problem, we would need to segregate students who play cricket in their free time based on highly significant input variable among all three.

This is where decision tree would help, it will segregate the students based on all values of three variable and identify the variable, which creates the best homogeneous sets of students (which are heterogeneous to each other).

In the picture below, you can see that variable Gender is able to identify the best homogeneous sets compared to the height and class.


As mentioned above, the decision tree identifies the most significant variable and its value that gives the best homogeneous sets of population.

Types of Decision Trees

Types of decision tree are based on the type of target variable we have. It can be of two types-

1. Categorical Variable Decision Tree- Decision Tree which has a categorical target variable is called a categorical variable decision tree. Example- – In the above example of student problem, where the target variable was “Student will play cricket or not” i.e. YES or NO.

2. Continuous Variable Decision Tree- If the decision Tree has a continuous target variable then it is called as Continuous Variable Decision Tree.

Now, let’s learn about some important terminologies related to Decision tree based algorithms in Machine Learning, as it will be very important for you to understand these terms if you want to delve deeper into the ‘Decision Trees’.

1. Root Node- It represents the entire population or samples, and this further gets divided into two or more homogeneous sets.

2. Splitting- It is the process of dividing a node into two or more sub-nodes.

3. Decision Node- When a sub-node splits into further sub-nodes, then it is called a decision node.

4. Leaf/ Terminal Node- Nodes that do not split are called Leaf or Terminal node.

5. Pruning- When we remove sub-nodes of a decision node, the process is called pruning. You can say the opposite process of splitting.

6. Branch / Sub-Tree- A subsection of the entire tree is called branch or sub-tree.

Now, the question which must have come to your mind must be, how and when to make a decision to split a decision tree.

The decision of making strategic splits heavily affects a tree’s accuracy. Hence, one has to be really careful while splitting a strategic tree.

Decision trees use multiple algorithms to decide to split a node into two or more sub-nodes.

The creation of sub-nodes increases the homogeneity of resultant sub-nodes. In other words, we can say that the purity of the node increases with respect to the target variable. Decision tree splits the nodes on all available variables and then selects the split which results in most homogeneous sub-nodes.

In this we will practically apply one of these algorithms named ‘Gini’; with the help of an example.

Gini defines, if we select two items from a population at random, then they must be of the same class, and the probability for this is 1 if the population is pure.

1. It works with the categorical target variable “Success” or “Failure”.

2. It performs only in Binary splits.

3. Higher the value of Gini, higher would be the homogeneity.

Steps to Calculate Gini for a split

Firstly, calculate Gini for sub-nodes, using the formula sum of the square of probability for success and failure (p^2+q^2).
2. Then, calculate Gini for split using weighted Gini score of each node of that split

Referring to the example used above, where we want to segregate the students based on target variable (playing cricket or not). In the image below, we split the population using two input variables Gender and Class. Now, we would identify which split is producing more homogeneous sub-nodes using Gini.


Split on Gender-

1. Calculate, Gini for sub-node Female = (0.2)*(0.2) + (0.8)*(0.8) = 0.68

2. Gini for sub-node Male = (0.65)*(0.65) + (0.35)*(0.35) = 0.55

3. Calculate weighted Gini for Split Gender = (10/30)*0.68 + (20/30)*0.55 = 0.59

Similar for Split on Class-

1. Gini for the sub-node Class IX = (0.43)*(0.43) + (0.57)*(0.57) = 0.51

2. Gini for the sub-node Class X = (0.56)*(0.56) + (0.44)*(0.44) = 0.51

3. Now we calculate weighted Gini for Split Class = (14/30)*0.51 + (16/30)*0.51 = 0.51

Above, you can see that Gini score for Split on Gender is higher than Split on Class, hence, the node split will take place on Gender. And since the node will split first in ‘Gender variable’, it is a better and more significant measure for this problem as showcased above with the basic approach of checking homogeneity.

So, we hope you have understood the concept of using Decision Trees and usage of Gini to split the root node. Do right your feedback and kindly ask doubts; if you have any