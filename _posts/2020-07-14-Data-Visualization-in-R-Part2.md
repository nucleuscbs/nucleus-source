---
layout: post
title: Data Visualization in R using ggplot2 (PART 2)
description: In the previous part of the series of blogs, we have covered the basics of visualization through ggplot2. But visualization is something which is not always simple and easy, there are many more dimensions to it. Read along as we explore some of them in today’s blog.

date: 2020-07-14
featured: no
---

![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Featured.jpg)
PLOT 11 - JITTER
![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot11 jitter.png)
So, what’s a jitter? Jitter is a random value that is assigned to the variable so they don’t fall on top of each other.

Code - ggplot(data=diamond, aes(y= price,x=cut,color=cut))  + geom_jitter(size=1.2, alpha= 0.5)


PLOT 12 - Box Plot

Code - ggplot(data=diamond, aes(y= price,x=cut,color=cut))  + geom_boxplot(size=1.2)

![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/2.png)

Box pot is a method to show data through their quartiles. The line in middle shows the median of the range. This gives us a hint about skewness and some other characteristics of the data.

The dots out of the box represent outliers. It is a useful tool to quickly represent outliers.

Here it can be observed that median of the premium quality cuts is higher, this sounds very reasonable because the premium quality does have high prices.

PLOT 13 -  Histogram

Code - ggplot(data=diamond, aes( x = price)) + geom_histogram(binwidth = 1000, color= “Blue”, fill= “White”)
![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/3.png)

The histogram represents the price of a diamond and the no. of diamonds in each price range. Binwidth here represents the width of each bar in the histograms. Please note that here colour represents the outline colour of the bar and fill represents the inside. A key take away from here is that almost more than 15000 diamonds lie in the range of 1000$-2000$. But remember, what we’ve tried now is setting i.e assigning one colour to the whole plot. Let’s try mapping -

PLOT 14 -  Mapping Histogram

Trying out mapping -

Code - ggplot(data=diamond, aes( x = price)) + geom_histogram(binwidth = 1000, aes( fill= clarity))
![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/4-Plot15-Adding Color.png)

Now we have the categorization based on clarity in each price range but the graph looks distorted and cluttered in. Let’s try to add a borderline to see a better view.

 PLOT 15 -  Adding Color

Code - ggplot(data=diamond, aes( x = price)) + geom_histogram(binwidth = 1000, aes( fill= clarity),color=”Black”)

The chart now looks good and is understandable. Let’s move on to explore facets now -

Facets --

Facets are used to create subdivision. For example - we want to see the price of each diamond concerning its cut independently. We will use facets to divide the diamonds according to their cuts. The code for creating distinct plots in one bar is – facet_grid(Rows~Columns).

Replace rows for dividing charts in the form of rows and columns for the same. Let’s try it out -

PLOT 16 -  Scatter Plot (Facet Version)

Code - ggplot(data=diamond, aes(x = carat ,y=price)) + geom_point() + facet_grid(clarity~.)



![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot-16-Scatter Plot.png)
Here, we have a relation between price and carat of each category of clarity. Each category of clarity has a different scatter plot in the form of rows. We would like you to try the same thing in the column form of facet_grid. Code would appear something like this -

Code - ggplot(data=diamond, aes(x = carat ,y=price)) + geom_point() + facet_grid(~Clarity)

PLOT 17 -

Now we’ll use both row and column

Code - ggplot(data=diamond, aes(x = carat ,y=price)) + geom_point() + facet_grid(clarity~cut)


![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot 17.png)

The chart now is depicting relationship between carat and price on the basis of the quality of cut as well as clarity.Let’s refine our chart to make it visually appealing.

PLOT 18 -  Refining Visualization

Code -  ggplot(data=diamond, aes(x = carat ,y=price)) + geom_point(aes(color= cut),size=0.5,alpha=0.5) + facet_grid(clarity~cut)+geom_smooth()

![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot 18 Refining viz.png)

We’ve reduced the size of the dots to make it easy for us to interpret. Smoother is added to identify trends, if there’s any. It can be seen from the chart that diamonds with I1 clarity and very good cut has almost equal price range as the premium cut. 
The cheapest diamonds are here seen to be of VVS2 category with fair cut, which makes sense.
Coordinates --

Co-ordinates deal with adjusting or zooming in and out of your coordinates. Let’s zoom in to one of the previously made visualizations.

Code - ggplot(data=diamond, aes( x = price)) + geom_histogram(binwidth = 1000, aes( fill= clarity),color=”Black”) + coord_cartesian(ylim = c(0,10000))

PLOT 19 -


The y-axis is zoomed in from (0-10,000), there is also another method of limiting your axes. You can similarly limit the x-axis as well. However, that method sometimes cuts your data and is not advisable. The code is given here, we would suggest you to try it yourself and identify this limitation.

![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot 19.png)
Code - ggplot(data=diamond, aes( x = price)) + geom_histogram(binwidth = 1000, aes( fill= clarity),color=”Black”) + ylim(0,10000)

PLOT 20 -

Let’s now try zooming in both the axes -

Code - ggplot(data=diamond, aes( x = price)) + geom_histogram(binwidth = 1000, aes( fill= clarity),color=”Black”) +

coord_cartesian(ylim = c(0,10000),xlim = c(0,10000))

![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot 20.png)

We’ve successfully zoomed in both the axes, we believe that is all there is tell about axes. Let’s move on to themes.

Themes --

Theme is all about formatting your axes labels, adjusting and positioning legend. This should’ve been done to every chart but you can of course go and apply this to every chart.

Let’s start with one of our most basic plots and start giving it the elements of themes.

Starting with labels and titles -

Code - ggplot(data=diamond, aes(y=price,x=carat, color= cut)) + geom_point(alpha=0.5) + xlab(“Diamond carat”) + ylab(“Price”) + ggtitle(“Relationship between Price and Carat”)

PLOT 21 -  Giving label


![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot 21 giving labe_.png)
The chart looks more descriptive, but there is still a lot of scope for improvement. Let’s try to change the font of labels.

PLOT 22 -  Adjusting Label

Code - ggplot(data=diamond, aes(y=price,x=carat, color= cut)) + geom_point(alpha=0.5) + xlab(“Diamond carat”) + ylab(“Price”) +

ggtitle(“Relationship between Price and Carat”) +

   theme(axis.title.x = element_text(color = “Dark Blue”, size = 30),

axis.title.y = element_text(color = “Dark Blue”, size = 30),

axis.text.x = element_text(size=20), axis.text.y = element_text(size=20))


![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot22 Adjust label.png)
Finally, Lets adjust labels and get done with it.

PLOT 23 -  Final Touch

Code - ggplot(data=diamond, aes(y=price,x=carat, color= cut)) + geom_point(alpha=0.5) + xlab(“Diamond carat”) + ylab(“Price”) +  ggtitle(“Relationship between Price and Carat”) +

   theme(axis.title.x = element_text(color = “Dark Blue”, size = 20),axis.title.y = element_text(color = “Dark Blue”, size = 20),axis.text.x = element_text(size=20),axis.text.y = element_text(size=20),legend.title = element_text(size = 15),legend.text  = element_text(size = 15),legend.position = c(1,1),legend.justification = c(1,1), plot.title = element_text(color=”Dark Blue”,size=20,family = “Courier”))


![Data Visualisation in R](/blog/Data Viz in R (Part 2)-20200902T032404Z-001/Data Viz in R (Part 2)/Plot23 final touch.png)
Finally, we’re done with everything. I would suggest you to try things on your own and experiment things in order to get a better view yourself.

Before proceeding towards visualization, it is highly suggested to be aware about all the elements of your data set and what is to be achieved from it.

GGPLOT2, in it has even more fascinating and useful tools. We suggest our readers to explore more of it and learn more about it.

The use of visualization techniques differ according to the purpose it serves but the underlying idea essentially remains the same. We hope that the basic idea and concept of visualization is clear to all of you. So, play around with these visualizations and do write to us in case of any queries. All the best!!!