# Intro to Machine Learning
### Machine Learning (ML)
Machine Learning is a set of algorithms used to develop and optimize computational models to accurately explain 
empirical data and its underlying phenomena with little human interference. ML is used to teach computers to perform a huge number
of tasks including speech recognition, object detection in images, image recognition, analysis and
information extraction from data in medical sciences and predictive analysis, to name a few.

### Types of Machine Learning
Broadly speaking, there are two types of Machine Learning:  
**Supervised:** refers to automatic learning involving input/output relationships. This is divided into two
forms: Regression and Classification  
**Unsupervised:** refers to automatic learning of the rules that describes input data only. This is often used
on the data to allow for easier supervised learning or for human interpretation. There are two unsupervised
problems: dimension reduction and clustering

## Supervised
### Classification
The classification is similar to the regression with the difference being that in regression one predicts a
continuous valued output while in classification the output takes discrete values or classes. Classification
has many applications like: object recognition where different images from a set are distinguished using
defined features, hand written digits, speech recognition etc.
The common way for classification in two dimensions is to find a dividing line or curve that separates the
two data sets.This task where we teach a computer to distinguish between different types or classes of
things (i.e. cats or dogs) is referred to as classification problem.

### Regression
Suppose we want to predict the share price of acompany. We first need to gather data consisting of
a number of companies (preferably in the samedomain as the one under consideration). Next, we
need to design features. A clear feature is the revenue- higher the revenue, higher is the share price. To connect the share price (output) to the
revenue (input), we train a simple linear model or regression line using our training data.
Example: student debt The student loan dept (measured quarterly) over
eight years period 2006- 2014. This has tripled over the 8 years period. The linear regression line shows the rapid increase in student debt and can be used to predict
this in future years.

## Unsupervised
### Dimension Reduction
The modern data today (images, videos, texts) have too large dimensions to allow development of
effective models. Reducing the dimension of a dataset means to project it down into a lower
dimensional line or curve, a linear hyperplane or non-linear manifold. The two dimensional data may be projected onto a
line and three dimensional data into a two dimensional hyperplane, reducing the dimension in each case by one.


### Clustering
Clustering identifies underlying structures in the data by grouping together points that share
some structural characteristics, like proximity to one another in the feature space. The structure
in the data can vary depending on data distribution and the feature space. In the clustering, data points lying close to one another
on the feature space have similar features and hence, can be considered as a cluster with common characteristics

### Optimization
Optimization is an important process in ML. We often formalize a search for parameters of a learning model via mathematical functions.
These are commonly referred to as cost or loss function. This finds the parameters in a model by finding the best fit (fit with minimum scatter)
to the data. A high value for the cost function is indicative of poor performance while a low value indicates optimum parameter fit.

View the next file here to find more information on Optimization 
