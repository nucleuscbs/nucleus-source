---
layout: post
title: K-Means Clustering
description: In our real lives we often face problems while choosing a perfect group for us. We look for various attributes and features among our group members that suits us the most and then decide whether to be a part of it or not. This process is often time consuming and may lead to inappropriate results. But in programming languages like R a simple few line code forms best clusters for you in say less than a minute. This is another feature that makes machines more efficient and unbiased in many areas including classification and clustering. So, let us start our tour of applications of machine learning from a simple but useful algorithm- K- means clustering.
date: 2020-05-20
featured: no
---
![K-Means Clustering](/blog/k mean clustering/K Means Clustering.png)
What is clustering?


Clustering refers to grouping of data under different groups based on their properties, nature, attributes and relationship. One cluster contains all the objects of similar nature that are atleast in some way different from other clusters. Clustering analysis is an essential part of both supervised and unsupervised learning. Whether exclusive (an item belongs exclusively to one cluster) or overlapping (item belongs to a number of clusters), it is of wide importance to all Data Scientists.


Categorizing news and articles into different groups like entertainment, sports, educational, political etc, spam filter (that automatically marks some mails as spam), classifying fake news, segmenting markets,  document analysis are some of the common real world applications of clustering algorithms.

K means clustering

K means clustering is one of the most popular clustering methods for unsupervised learning with wide application. It iteratively calculates the deviation from a point called centroid. Initially K number of so called centroids are chosen. A centroid is a data point (imaginary or real) at the center of a cluster. The initial centroids are randomly selected and then each data point is mapped to closest centroid. The second centroid is moved to mean of each cluster it defines. This is iteratively done till convergence or till the clusters become constant and centroid and composition of cluster no longer changes.
![K-Means Clustering](/blog/k mean clustering/1_IXGsBrC9FnSHGJVw9lDhQA.png)

Let us understand the concept with a simple inbuilt dataset in R. Suppose, we have a list of Sepal length and Sepal width of various species of flowers and for their nomenclature it is required to put them into appropriate clusters. These species are unknown to us and we can’t simply put them anywhere. That is when clustering comes into the picture. To be more precise this is when K-Means Clustering comes in.

Let us first start with loading the dataset. To avoid the trouble of downloading a dataset from the internet we have used a popular dataset inbuilt in R- IRIS. Let us look at it first. A brief overview of the data and detection of NAs will clean it for us to start.

install.packages(“datasets”)

library(datasets)

str(iris)

table(is.na(iris)) 


This summarizes the dataset for us with 5 variables and 150 observations and to our utter delight no NAs. The dataset is now all set to work upon.

We now divide our datasets into two parts– try and test. Although not essential but this little step helps us to appreciate the reliability of our models. We run it on train dataset and then introduce the test dataset to our model to check how well it works in unknown variables.

parting<-sample(2, nrow(iris),replace=TRUE, prob=c(0.5,0.5))

try<-iris[parting==1,]

test<-iris[parting==2,]


For K means this has to be then converted into a matrix. We select the columns which will form the basis for clustering. Though, we have used sepal length and sepal width you are free to try all possible combinations and write to us if you explore something more insightful.

try.short<-try[,c(1,2)]

try.matrix<-data.matrix(try.short)    

Now, since we are all equipped; let’s use K means.

Syntax of K-means function in R…

Object=kmeans(x, centers, iter.max=, nstart=)

x => Data matrix of data to be clustered  
centers => Number of clusters
iter.max => Maximum iterations
nstart => Number of centers to start with
A two line code will print a half page result. Big but significant.

traincluster<-kmeans(try.matrix,3)

traincluster


traincluster$size

traincluster$centers

This way the additional arguments can be used for specific and detailed results.

K means clustering have classified the data into three categories each possibly belonging to different species on the basis of their distance from mean sepal length and sepal width.

Visualizing the clusters make the results more attractive and comprehensible.

Install.packages(“ggplot2”)

Library(ggplot2)

traincluster$cluster<-as.character(traincluster$cluster)

ggplot()+geom_point(data=try, mapping=aes(x=Sepal.Length,y=Sepal.Width, color=traincluster$cluster)) +geom_point(mapping=aes_string(x= traincluster$centers[,”Sepal.Length”], y=traincluster$centers[,”Sepal.Width”]), size=4,color=”red”)



Within Cluster Sum of Squares

The sum of the squared deviations from each observation and the cluster centroid is called as within- cluster sum of square. The within-cluster sum of squares is a measure of the variability of the observations within each cluster. In general, a cluster that has a small sum of squares is more compact than a cluster that has a large sum of squares. Clusters that have higher values exhibit greater variability of the observations within the cluster. As the number of observations increases, the sum of squares becomes larger. Therefore, the within-cluster sum of squares is often not directly comparable across clusters with different numbers of observations. To compare the within-cluster variability of different clusters, use the average distance from centroid instead.

Determining the optimum number of clusters (Elbow method)

wss<-(nrow(try.matrix)-1)*sum(apply(try.matrix,2,var))

for(i in 2-15)

    wss[i]<-sum(kmeans(try.matrix,centers=i)$withinss)

a<-plot(1-15,wss,type=”b”,xlab=”Number of Clusters”,ylab=”Within Cluster Sum of Square”)

Elbow method brings out the graphical representation of various combinations of within cluster sum of squares and number of clusters. So, usually a elbow like structure is formed. Considering that we require lower within cluster sum of squares, we use that number of cluster where bent of elbow is achieved. This shows a sharp decrease in within cluster sum of square with increasing a cluster and after this within cluster sum of squares tends to be constant. And this nearly constant within cluster sum of squares is often not useful because it arbitrarily increases the number of cluster and makes them all more homogeneous.



So, in the above graph we see that WSS significantly reduces from  1st to 3rd cluster, so here optimum clusters are 3.

Prediction and clustering

If we are using clustering to predict about the some categorical variable with same level of factors as we have the clusters, we can check the accuracy using simple table or even the confusion matrix

table(traincluster$cluster,try$species)

This would give us the number of values that are correctly predicted and number of that are incorrect. Since, clustering is part of unsupervised learning , we do not test the model accuracy. But for the sake of developing a understanding and reliability of the model this hack could be used. This alongwith some other tools like confusion matrix is used while we use clustering as part of supervised learning environment.

So, we hope that you have understood the concept through our blog. Do write your precious feedback and feel free to ask any related doubt.