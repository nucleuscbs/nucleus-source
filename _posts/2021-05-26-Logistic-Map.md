---
layout: post
title: MAPPING POPULATION GROWTH WITH LOGISTIC MAP
description: The logistic map is a polynomial mapping (equivalently, recurrence relation) of degree 2 which exhibits how from very simple non-linear dynamical equations; complex, chaotic behavior can arise.
date: 2021-05-26
featured: no
---

<img src="/blog/LogisticMap/TheLogisticMap.png">

Did not understand?! Don't worry we are here to make it simple. But let's dive into some history first.

Popularized in 1976, by Robert May (a biologist), which was related to the logistic equation written down by Pierre François Verhulst.

Mathematically, the logistic map is written as:

<img src="/blog/LogisticMap/Equation.jpeg">

Where xn is a number between zero and one that represents the ratio (percentage) of the existing population to the maximum possible population.

The values of interest for the parameter r (sometimes also denoted μ) is the growth rate of the population.
Here xn+1 shows the population in the next period (Let’s assume a period to be of a year here).

To understand its real-life application let’s take the following case:

CASE

Analyse the population of a species by using The Logistic Map equation. Remember Darwin’s famous lines “Survival of the fittest” which means that organisms of a species do compete for resources for survival. Remember this is just a theoretical equation. Population sizes in real life scenarios may vary significantly due to changes in many factors and figures.

Here the objective is to define how ‘The Logistic Equation’ fits into the patterns of population growth-

ANALYSIS

Firstly, defining the situation and the variables used

Population (Xn) is expressed as a percentage of the maximum possible population (which could have exhausted the entire resources available).

The rate of growth (r) is the growth rate at which Xn percentage of populations is growing (i.e., the percentage of the maximum possible population).

Before you begin with the analysis, you have to make certain assumptions to understand the nature of the population growth:

Population is able to develop the resources available to it, which is done by any naturally existing population.

The population takes into account that some organisms would be younger and others older. (i.e., not all the organism of the population are of the same age).

Organisms in the population fight for the resources to survive.

Now what you have here is a python code you can use to draw the graphs that are going to be referred to below.

{CODE STARTS HERE}

import matplotlib.pyplot as plt

#Enter the GROWTH_RATE(R), INITAL_POPULATION(Xn), and NO. OF YEARS YOU WANT TO SHOW THE PROJECTION FOR

growth_rate = float(input("Enter the growth rate for the population: "))

initial_population = float(input("Enter the initial population (i.e. population for the first year): "))

years = int(input("Enter the no. of years you want to find the projection for: ")) + 1

def logistic_equation(initial_population, growth_rate):

population_next_year = growth_rate*initial_population*(1-initial_population)

return population_next_year

x = [0]

y = [initial_population]

for i in range(0, years):

initial_population = logistic_equation(initial_population,growth_rate)

x.append(i+1)

y.append(initial_population)

plt.plot(x, y, color = 'green', linestyle = 'solid', marker = 'o', markerfacecolor = 'red', markersize = 9)

plt.title("Population growth at " + str(growth_rate) + " Growth Rate")

plt.xlabel("Year no.")

plt.ylabel("Population (as a percentage of max population)")

plt.show()
{CODE ENDS HERE}

In the graphs you have:

At
r = 0.49 and Xn = 0.4

The following Is the graph for population projection over 50 years:

<img src="/blog/LogisticMap/Figure_1_Population_GrowthRate.png">

Here you can see that after a certain no. of years it becomes 0.

Next let’s take

r = 0.99 and Xn = 0.4

A projection for 50 years reveals such an image:

<img src="/blog/LogisticMap/Figure_2_Population_GrowthRate.png">

Here also, the population becomes extinct beyond 50 years of growth.

Now following are the graphs for:

r = 1.49 and Xn = 0.4
<img src="/blog/LogisticMap/Figure_3_Population_GrowthRate.png">

r = 2.37 and Xn = 0.4

<img src="/blog/LogisticMap/Figure_4_Population_GrowthRate.png">

r = 3 and Xn = 0.4

<img src="/blog/LogisticMap/Figure_5_Population_GrowthRate.png">

r = 3.49 and Xn = 0.4

<img src="/blog/LogisticMap/Figure_6_Population_GrowthRate.png">

What you observe in graph 1, 2, 3 is that the growth rate of less than 1.6(BAR) resulted in a continuous fall in population ultimately leading to its extinction in some future years.

In graph no. 2, you observe that there was some chaotic movement in the initial years but in the later years the population attained equilibrium resting itself at 0.575 approximately.

In the graph 5 & 6, you can see a cyclic movement as population goes through a cycle of 2 every consecutive year and a cycle of 4 every consecutive year respectively.

What one can analyse from this data is how well this simple mathematical operation exhibits the working of a real-life population as follows:
When the growth rate was low at a population of 40% (of what can be the maximum population) the population became 0 by the 10th year.

This explains how a small population with a low growth rate can become extinct over the years as they will not perish. New ones will not be born and old ones will die. This leads to continuous deduction in adults who can reproduce. Leading to the extinction of the species.

When the growth rate reached 0.99 the fall in population was gradual but in growth rate 1.49 the fall was again steep. Does this defy the 1st analysis?

The answer is No.

What happens here is as the small population grows at a rate of 0.99 it can sustain itself since the population can be fed considerably, reproduce and still survive for a countable 50+ years but ultimately become extinct in a certain year.

However, for the growth rate of 1.49 the fall is steep as the increased population creates competition for resources. This is not good as this leads to the fight for survival, which leads to premature deaths. Even if you keep into account the increased no. of the population as a resource still many will not be able to become of any use and be reduced for the lack of resources.

When the growth rate reached 2.37 it was the right growth rate as the population was able to sustain itself. The growth rate was just right for the population to be fed, taught/learn(Itself in case of unicellular and mute species), to reproduce future progenies. Ultimately they reached an equilibrium population that can thrive forever if the growth rate is stable (which does not happen in normal cases).

Surprisingly when the growth rate reaches 3 you can see cyclic population growth. One year it increases and the other it decreases. This is because there are constant cases of lack of resources which leads to a decline in population in one year, but as soon as the population declines it again grows back the next year only to decline the other and repeat the cycle.

If you go on increasing the rate the cycle will disperse its repetition intervals. Now instead of 2-year, you observe a 4-year cycle. The reason again being the same scarcity of resources in one year and abundance in the other.

When you increase growth rate beyond 4 it rises suddenly and then falls to almost a nil compared to the previous year, then rising and falling erratically, finally going to be 0 at some future year, which again comes somewhere after 10 years or so as seen in CASE 1.

(In this case, you can see a negative population which can be neglected as the population can never be negative.)

For low values of R you see the populations always go extinct so the equilibrium value is zero, but once R hits 1 the population stabilizes on to a constant value and the higher R is the higher the equilibrium population, but once R passes three the graph splits in two.

The equation never settles on to a single constant value instead it oscillates back and forth between two values one year the population is higher the next year lower and then the cycle repeats the cyclic nature of populations is observed in nature to one year there might be more rabbits and then fewer the next year and more again the year after.

This was a simple equation starting with only 2 variables which can help us understand the nature of population growth. Now comes the reason, where can it be applied.

By now you should have had a fair idea of it, some places where its expected to return good returns would be:
Understanding sustainable population growth rates for a current population.

How to track population growth of a certain organism (for eg. Bacterial growth) and ways to eradicate or sustain it (either through low growth rates or by very high growth rates.)

Creating equilibrium populations for different species in an environment and understanding how long the different species' populations will survive.

(Just a hypothetical example) It can be used to eradicate the zombie population if there is a probable outbreak in the future.
These were some of the applications on biology. It can be applied to other fields also as it has been able to define:

The rhythmic pattern of a dripping faucet

Thermal convection in a fluid
And, The firing of neurons in your brain

So, fire your neurons right away and figure out how you can use this equation to predict chaos in population growth rate or any other growth rate in your field interest.
