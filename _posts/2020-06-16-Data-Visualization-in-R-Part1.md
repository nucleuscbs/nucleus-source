---
layout: post
title: Data Visualization in R using ggplot2 (PART 1)
description: How difficult is it, to look at loads of data in front of you and not being able to summarize it Insightful visualization is an important aspect of Data Analytics. But, don’t worry that’s what we are here for, to demonstrate to you one of the best Data Visualization tools in R which will make your life easier. By now, you must have known the answer yourself. Yes, GGPLOT it is. It is said to be based on the Grammar of Graphics which aims at creating Plots layers by layers and each layer refines the plot in its own way. Let’s have a look at these layers before proceeding further.
date: 2020-06-16
featured: no
---
![Data Visualization](/blog/Data Visualization in R Part1.jpg)
![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/1.png)

s this image speaks for itself, we think this gives enough clarity about the elements, which are essential in making the plot. Before we proceed further, we’d like to tell that the first 3 layers are the essentials to making a plot.Otherwise, we’ll have nothing but an empty graph. Now, as the old saying goes “learn by doing”. We’ll jump on to GGPLOT, start from the basics and explore all layers.

Let’s Begin

As you know before starting anything we need to make sure we’ve installed the package and activated it in our library. Please note the code for installing and activating the package

Instal.package(“ggplot2”)

library(ggplot2)

As soon as the package is installed and the data set is imported, we will start working on the visualization part.

Please do follow the codes and practice them simultaneously on R for a thorough and complete understanding of these beautiful visualizations.

Dataset Link- https-//vincentarelbundock.github.io/Rdatasets/datasets.html

PLOT 1 - Blank Graph

The data taken here is life expectancy over the years in India since 1960.

Code - ggplot(data= life_expectancy, aes(x=expectancy, y = Years))
![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot 1-blank graph.png)

As you can see, the plot is empty; this is because the minimum 3 elements i.e data, aesthetics, and geometries are not supplied in the code. The plot does contain data and aesthetics but before knowing what type of geometry is to be made, how can anything move forward?

PLOT 2  - Scatter Plot

Let’s make a simple point chart!

ggplot(data=x, aes(x=years, y=Expectancy) + geom_point
 Now that we’ve added geometry the plot is finally formed with a scatter plot.
![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot2 scatter plot.png)

MOVING FORWARD!

But why would anyone go through all the trouble of making a visualization as simple as this, which can even be made in Excel? So let us look at some things which cannot be done in Excel. The data set we have taken has 6 columns. It is a data set of different categories of diamond according to their price, cut, clarity and some other elements.

PLOT 3 -  Scatter Plot

Preview of the data can be taken by

Summary(diamonds)



ggplot(data = x, aes(x=carat,y=price)) + geom_point()
![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot 3.png)

The plot is again a simple scatter plot with the relationship between price and carat. It can roughly be concluded that there exists a positive relationship between price and carat i.e as the carat increases price also increase. But again, this can also be done in excel, then why should we prefer R over excel? Let’s try to build over this only-

PLOT 4-  Adding Colors and Size

Now what If you want to work with more than 2 variables? let’s say we want to see the price, carat as well as the cut in each carat category and its price

Code - ggplot(data=diamond, aes(y=price,x=carat, color= cut)) + geom_point()


Now,we have Price of diamonds with each carat along with the cut, so the color signifies the quality of cut in each category and its price.So, now we have a strong reason for choosing R over excel when it comes to visualizing big data

Even 3 variables is not enough and we want to classify the data  on the basis of the size too.

Code - ggplot(data=diamond, aes(y=price,x=carat, color= cut,size=depth)) + geom_point()

![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot4.png)

As you can see the size of the points is adjusted according to the depth. The description is given in the legend. However, the plot looks horrible and hardly any interpretation can be made from it. It is just to give you an idea of how elements can be used.

SIMPLIFYING CODING

PLOT 5 -  Scatter Plot

It gets tedious to add again and again the primitive part of the code and then to add layers when it is nothing but the same code? 

So ,we will store the code in an object to save us from the labor work and make things easier.

Code - q <- ggplot(data=diamond, aes(y=price,x=carat, color= cut))

We have saved the code in ‘q’ we don’t need to do anything but build layers on top  of the basic structure

q + geom_point()

![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot5.png)

It gave you the same result as plot 5 just with a lot of ease. You can develop a basic code store it an object just like we did and then explore your data set with convenience

OVERRIDING AESTHETICS

Now that we’ve stored our basic plot details such as data and aesthetics, what if we change our mind and now we want different variables in the x and y-axis. Don’t you think going back and changing the plot again and storing it would be a lot of work? If yes, then you can try a thing called overriding aesthetics, all you need to do is re-enter the new aesthetics in your geometry, which in our case is geom_point. This will override the previously entered aesthetics in our basic object i.e ‘q’ and give us a greater flexibility and encourage to explore even more. Let’s try it out! 

Code - q + geom_point(aes(x= depth, y = price)) + xlab(“Depth”)

PLOT 6

![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot6.png)

The object q already had a command of depicting the relationship between price and carat but the command in geom_point overrode the command present in the basic plot. Hence, we will display the relationship between depth and price. Now you must be wondering why we had to put a label on the x-axis. This is because one of the limitations of overriding aesthetics is that the label doesn’t get changed. Hence, in this case if it weren’t for me changing the label. The label would’ve been Price and Carat giving out a false representation of the data. This is why you have to be extremely careful while overriding aesthetics. 

MAPPING VS  SETTING

Mapping is what we’ve been doing till now i.e assigning colorsto a level detail. That means colour here is signifying a bifurcation based on different characteristics of the data set. Plot 4 is a perfect representation of mapping. But what if we don’t want to add color to a level of detail, we just want to change the color from black to Red. That’s where the setting comes in. Assigning one color to the whole data set is called setting. Let’s try it out.

PLOT 7 - SETTING

![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot7.png)
Code - q + ggplot(aes(x= depth, y = price), color= “Red”) + xlab(“Depth”)


This is what setting is, assigning a whole new color to the data set. Please note, while setting a color we don’t use a prefix of “aes”. Using aes will cause a misunderstanding and lead to an error. Hence, be cautious with that. We think we don’t need to present mapping as it has already been presented in the former part. We’ve explored the aesthetics enough, now let’s move to on exploring geometries.

PLOT 8 - Line Chart

How about we make a line plot instead of a scatter plot

Code - ggplot(data=diamond, aes(y= price,x=carat)) +  geom_smooth(fill=NA)

![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot8.png)

This chart is simply depicting the relationship with carat. However, this chart in itself is not that informative, so lets also add some more geometries in it.

 
PLOT 9 - Line Plot + Scatter plot

Code  - ggplot(data=diamond, aes(y= price,x=carat)) + geom_point() +  geom_smooth(fill=NA)


![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot9.png)
This looks better. But, still it can be misleading as carat is not only deciding factor of price and looking only on this relationship independently can be misleading

PLOT 10 - Mapping Clarity

To solve the problem let’s add variable  ‘clarity’ to our plot
Code - ggplot(data=diamond, aes(y= price,x=carat,color=cut)) + geom_point() + geom_smooth(fill=NA)

![Data Visualization](/blog/Data Viz in R Part 1-20200902T032430Z-001/Data Viz in R Part 1/plot10.png)

We believe this gives a better picture of the prices as the data depicts the prices according to carat as well as clarity
So, we hope that you must have understood the concept of visualization using ggplot2 in R. Worry not, because we will be posting the second part soon covering even more insightful and amazing visualization techniques under ggplot2. Hit the like button, if you liked our post; and subscribe our blog to be connected to us, as many more wonderful topics are underway-)