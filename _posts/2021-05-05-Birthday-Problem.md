---
layout: post
title: The Birthday Problem
description: What is the probability of two people sharing the same birthday in a room of n people?
date: 2021-05-05
featured: no
---

<img src="/blog/BirthdayProblem/BirthdayProblem%20(1).png">

Alternatively, how many people must be there in a room such that the probability of two people sharing the same birthday is pretty high, 50% to 90%? Quite intriguing questions, right? Think about the problem before reading further on. Assume that there are no twins in the room, the no. of days in the year is 365 (sorry people who have birthdays on 29th Feb) and the distribution of birthdays throughout the year is uniform (Actually it's the worst case, the results will be even better in real-world scenarios because the birthdays are more closely distributed in the real-world than the ideal world of uniform distribution).

The Math

Let’s turn to math for an answer because our intuition can be wrong (wasn’t yours?) but math can’t be wrong. We as humans are a bit selfish (weren’t you thinking about your birthday matching with someone else, rather than any two people having the same birthday). Combinatorics tells us that there are nC2 pairs possible when we take any 2 people from the total of n people in the room.

For these calculations, we’ll make a few assumptions. First, we’ll disregard leap years. It simplifies the math without having too great an effect on the results. Second, we assume that birthdays are uniformly distributed throughout the year and have an equal probability of occurring (However, that is not usually the case. Studies have shown that more people are born in the first half of the year in India than the second, especially from April to June). Taking uniform distribution gives a truer mathematical approximation as the probability of two people sharing the same birthday is the least in case of uniform distribution.

We’ll start with one person, and then add people in one at a time to illustrate how the calculations work. It is simpler to find the probability that no one shares a birthday. We’ll then take that probability and subtract it from one to derive the probability that at least two people share a birthday because these two are complements of each other.

Using, P(A) = 1 - P(A’),

Probability of at least one same birthday = 1 – Probability of no same birthday

For the first person, there are no birthdays already reserved, which means that there is a 365/365 chance that there is not a shared birthday. That makes sense since we have only one person.

<img src="/blog/BirthdayProblem/BirthdayProblem%20(2).PNG">

Adding a second person to the mix gives us an interesting result. The first person covers one possible birthday, so the second person has a 364/365 chance of not sharing the same day. To find the probability of no match, we’ll multiply the probabilities of the first two people and subtract from one to calculate the probability of them sharing the same birthday.

<img src="/blog/BirthdayProblem/BirthdayProblem%20(3).PNG">

When the third person comes, the previous two people already cover two dates. So, the third person has a probability of 363/365 for not sharing a birthday.

<img src="/blog/BirthdayProblem/BirthdayProblem%20(4).PNG">

The pattern for how to calculate the probability for a given number of people must be quite visible now, though no worries if you couldn’t figure it out. Here’s the general form of the equation:

<img src="/blog/BirthdayProblem/BirthdayProblem%20(5).PNG">

By assessing the probabilities, the solution to the Birthday Problem is that you need a group of 23 people to have a 50.73% chance of people sharing a birthday! Most people expect the group to be considerably larger than that (what was you guess?). The chart also depicts that a group of 57 has a probability of 0.99. It’s practically a guarantee that in a group of 57 people, two will share a birthday.

<img src="/blog/BirthdayProblem/BirthdayProblem%20(6).png">

(Credit: statisticsbyjim.com)

Explaining the small size of the group.

People consider the answer to the Birthday Problem difficult to believe: How can it be so small? However, the answer is correct, proven by probability and statistics. When thinking of the problem, people usually consider themselves. However, it could be any two people in the group. If we pair each person with another, this leads to the formation of a large number of pairs and therefore increases the possibility of the twin-birthday pair. The number of different pairs or unique combinations formed for 23 people (probability of 0.5) is 253.

=> nC2 = 23C2 = 253

As seen earlier, each pair’s probability of sharing a birthday is 0.0027, but for 253 pairs that number changes drastically.

Similarly, when there are 57 people when the probability is ~1, you have 1596 pairs. Now, we would find it absurd if none of the pairs share a birthday.

=> nC2 = 57C2 = 1596

Conclusion

We conclude that intuition doesn’t work in such problems because we humans are pretty bad at visualizing nonlinear functions and grossly underestimate the number of pairs formed from n number of people. Mathematics and statistics hence come to our rescue and prove to be pretty useful in such situations. So next time whenever you are in a room with 50 people make sure to find your birthday match.
