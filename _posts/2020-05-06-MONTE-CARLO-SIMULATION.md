---
layout: post
title: MONTE CARLO SIMULATION
description: Simulation is basically a process of designing a model and conducting simultaneous experiments within the model to understand the behaviour of the system.

date: 2020-05-06
featured: no
---
![K-Means Clustering](/blog/2020-05-06-MONTE-CARLO-SIMULATION/MONTE CARLO SIMULATION.jpg)
It is pertinent to note that Monte Carlo Simulation provides a probabilistic estimate of the uncertainty in a model. It is never deterministic. However, given the uncertainty or risk ingrained in a system, it is a useful tool for approximation of realty.

HISTORY
Monte Carlo simulation has been named after the city in Monaco ( which is famous for its casino) where games of chance (e.g., roulette) involve repetitive events with known probabilities. Mathematician Stanislaw Ulami developed the technique while working on nuclear weapon projects during the World war II era.

APPLICATION
The method is used extensively in a wide variety of fields such as physical science, computational biology, statistics, artificial intelligence, and quantitative finance.

It can be used in virtually any field such as- Statistics, Artificial Intelligence, finance, engineering, physical sciences, law etc.

For example, it can be used in the word of business and finance. The MCM is used to price financial instruments and also plays a critical role in risk analysis. It also used to solve complex business problems relating to consultancy and forecasting future trends of business performance


The above picture is a basic example of MC Simulation. It shows the net return of an index after 5 years given the mean and standard deviation.
We have prepared an MC Simulation, you can check it out-
https-//bit.ly/MCSimul


EXAMPLE
Let’s consider calculating the probability of a particular sum (7) on the throw of 2unbiased dice. So, there are total 36 combinations of dice rolls-

There are 6different ways that the dice cab sum to 7. Hence, the probability of rolling 7 = 0.167.

Instead, we can throw the dice a hundred times and record how many times each outcome occurs. If the dice totals 7, 18 times (out of 100 rolls), we would conclude that the probability of getting the sum 7 is approximately 0.18 (18%).Better than rolling the dice a hundred times, we can easily use a computer to simulate rolling the dice n times. The output of 10,000 realizations-

Two Dice
HOW ACCURATE ARE THE RESULTS
The accuracy of a Monte Carlo simulation is a function of the number of realizations. That is, the confidence bounds on the results can be readily computed based on the number of realizations. The example below shows the 5% and 95% confidence bounds on the value for each outcome (i.e., there is a 90% chance the the true value lies between the bounds)-

