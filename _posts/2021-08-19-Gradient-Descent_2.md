---
layout: post
title: Gradient Descent
description: Over the years, many optimization techniques have been developed for machine learning algorithms and neural networks. One such sound technique is Gradient Descent. Read along to learn about this amazing algorithm and how it can be implemented to help us solve complex optimization problems.
date: 2021-08-19
featured: no
---
<img src="/blog/2021-08-19-Gradient-Descent/9.png">

<h2>Introduction</h2>

Optimization is an important part of our life. We all have limited resources and time and we wish to make the most of them. From utilizing resources effectively to solving problems for an organization – everything uses optimization. Optimization is required everywhere whether you are working with a real-life problem or building a product.

Optimization means getting the optimal solution for your problem. 

Optimization starts with very simple and basic problems, but it can get very complex sometimes. For example, allocating a monthly household budget is a simple optimization problem. On the other hand, devising various strategies for any organization company can be very complex.

Linear regression is a simple optimization problem. The representation is a linear equation that uses a specific set of input values/training data values (x) and a predicted output value/test set values (y).

So in machine learning, we perform optimization on the training data and check its performance on newly defined test data.

Many popular machine algorithms depend upon optimization techniques such as linear regression, k-nearest neighbors, neural networks, etc. The applications of optimization are limitless and are a widely researched topic in both academia and industries.

Gradient Descent is the most commonly used optimization technique when dealing with machine learning.

<h2>What is Gradient Descent?</h2>

It is an optimization algorithm to reduce the cost of the function. We start with any random point on the function since we are unaware of the direction where we will obtain the most optimal solution and move in the <b>opposite direction</b> of the <b>gradient of the function</b> to obtain the <b>local/global minima.</b>

<img src="/blog/2021-08-19-Gradient-Descent/7.jpg">

To understand the distinction between local and global minima, let’s take a look at the figure above. The global minimum is the least value of any function while a local minimum is the least value of a function in a certain neighborhood.

To explain Gradient Descent, we will use the standard example of hill descending.

Consider a valley on which you are standing. Now your task is to reach to the lowest point of the valley. A twist is that you are blindfolded and you have no visibility to see where you are heading to. So let's understand what approach can be used for this problem

The best way is to check the ground near you and observe where the terrain tends to descend or decrease. This will give you a good idea of what direction you must take your first step. If you follow the descending path, you would probably reach the bottom of the camp.

To represent this graphically, let’s have a look at the below graph.

<img src="/blog/2021-08-19-Gradient-Descent/6.jpg">

Let us now map this scenario in a mathematical formula.

We have to start with some θ0  and θ1. We need to keep changing the parameters to reduce the cost function until we hopefully end up at a minimum.

The algorithm of gradient descent can be written as follows

<img src="/blog/2021-08-19-Gradient-Descent/5.jpg">

So, on the y-axis, we have the cost function J(θ) along with the parameters θ1 and θ2 on the other two axes.

Now there are some kinds of gradient descent algorithms that can be further classified as follows:
<br>
<br>
<b>● On the basis of data ingestion</b>
1. Full Batch Gradient Descent Algorithm
2. Stochastic Gradient Descent Algorithm

For full batch gradient descent algorithms, we use the complete data along with all the parameters to compute the gradient, whereas, for stochastic algorithms, we take only a small sample of the data.
<br>
<br>
<b>● On the basis of differentiation techniques</b> 
1. First-order Differentiation
2. Second-order Differentiation

Gradient descent calculates gradient by differentiating the cost function. To take the derivative of the cost function, either first-order or second-order differentiation can be used.
 
<h2>Challenges in executing Gradient Descent</h2>

Gradient Descent is a binding technique that works in most cases. But there are various cases where gradient descent doesn’t work properly or fails to find an optimum value. The major reasons for its failure are as follows:
1. Data challenges
2. Gradient challenges
3. Implementation challenges
 
<b>A. Data Challenges</b>
<br>
● Gradient Descent has a very low convergence rate and thus the answer is obtained in several iterations, consuming a lot of time and effort.
<br>
● There is also a saddle point problem. This is a point in the data set where the gradient is zero and it is thus not an optimal point.
 
<b>B. Gradient Challenges</b>
<br>
● If the learning parameter becomes extremely large, the method of Gradient Descent can overshoot the minimum, it may fail to converge or even diverge.
<br>
● One of the other problems of this approach is converging to a local minima can be quite slow. If there are multiple local minima present in the dataset, then there is no guarantee that the algorithm will detect the global minimum.
 
<b>C. Implementation Challenges</b>
<br>
● When implementing the algorithm of gradient descent, it is extremely important to calculate how many resources one would need. If the memory is too small, then the network would fail.
<br>
● Also, it’s important to keep track of floating-point data values and hardware/software prerequisites.
 
<h2>Conclusion</h2>

The method of Gradient Descent can also be used for multiple regression when we have multiple features/parameters. To improve Gradient descent for multiple features, methods like Feature Scaling, Mean normalization, and Debugging can be used.
Gradient Descent can be used for both Linear and Logistic Regression machine learning algorithms. This method is a standard method of minimizing the cost function which works well for every machine learning algorithm.
