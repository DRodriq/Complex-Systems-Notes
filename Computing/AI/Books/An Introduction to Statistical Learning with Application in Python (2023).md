## Contents
### Introduction
### Statistical Learning
#### What is Statistical Learning
#### Assessing Model Accuracy
#### Lab: Introduction to Python
#### Exercises
### Linear Regression
#### Simple Linear Regression
#### Multiple Linear Regression
#### Other Considerations in the Regression Model
#### The Marketing Plan
#### Comparison of Linear Regression with K-Nearest Neighbors
#### Lab: Linear Regression
#### Exercises
### Classification
#### An Overview of Classification
#### Why Not Linear Regression
#### Logistic Regression
#### Generative Models of Classification
#### A Comparison of Classification Models
#### Generalized Linear Models
#### Lab: Logistic Regression, LDA, QDA, KNN
#### Exercises
### Resampling Methods
#### Cross-Validation
#### The Bootstrap
#### Lab: Cross-Validation and the Bootstrap
#### Exercises
### Linear Model Selection and Regularization
#### Subset Selection
#### Shrinkage Methods
#### Dimension Reduction Methods
#### Considerations in Higher Dimensions
#### Lab: Linear Models and Regularization Methods
#### Exercises
### Moving Beyond Linearity
#### Polynomial Regression
#### Step Functions
#### Basis Functions
#### Regression Splines
#### Smoothing Splines
#### Local Regression
#### Local Regression
#### Generalized Additive Models
#### Lab: Non-Linear Modeling
#### Exercises
### Tree-Based Methods
#### The Basics of Decision Trees
#### Bagging, Random Forests, Boosting, and Baynesian Additive Regression Trees
#### Lab: Tree-Based Methods
#### Exercises
### Support Vector Machines
#### Maximal Margin Classifier
#### Support Vector Classifiers
#### Support Vector Machines
#### SVMs with More than Two Classes
#### Relationship to Logistic Regression
#### Lab: Support Vector Machines
#### Exercises
### Deep Learning
#### Single Later Neural Networks
#### Multilater Neural Networks
#### Convolutional Neural Networks
#### Document Classification
#### Recurrent Neural Networks
#### When to Use Deep Learning
#### Fitting a Neural Network
#### Interpolation and Double Descent
#### Lab: Deep Learning
#### Exercises
### Survival Analysis and Censored Data
#### Survival and Censoring Times
#### A Closer Look at Censoring
#### The Kaplan-Meier Survival Curve
#### The Log-Rank Test
#### Regression Models with a Survival Response
#### Shrinkage for the Cox Model
#### Additional Topics
#### Lab: Survival Analysis
#### Exercises
### Unsupervised Learning
#### The Challenge of Unsupervised Learning
#### Principal Components Analysis
#### Missing Values and Matrix Completion
#### Clustering Methods
#### Labs: Unsupervised Learning
#### Exercises
### Multiple testing
#### A Quick Review of Hypothesis Testing
#### The Challenge of Multiple Testing
#### The Family-Wise Error Rate
#### The False Discovery Rate
#### A Re-Sampling Approach to p-Values and False Discovery Rates
#### Lab: Multiple Testing
#### Exercises
### Index
## Outline
### Preface
In addition to a review of linear regression, ISLR covers many of today’s most important statistical and machine learning approaches, including resampling, sparse methods for classifcation and regression, generalized additive models, tree-based methods, support vector machines, deep learning, survival analysis, clustering, and multiple testing.
### Introduction
Statistical learning refers to a set of tools for understanding data. These tooks can be classified as supervised or unsupervised. Basically, supervised statistical learning consists of building a statistical model for estimating an output based on one or more set of inputs. 
**Brief History**
19th century - Least Squares Method, implementing Linear Regression. 
1930-1940s - Linear Discriminant Analysis, Logistic Regression\
1970s - Generalized Linear Model generalized an entire class of methods including linear and logistic regression
1980s - Nonlinear Methods, Classification and Regression Trees, Generalized Additive Models, Neural Networks
1990s - Support Vector Machines
**Four Premises of this Book**
- *Many statistical learning methods are relevant and useful in a wide range of academic and non-academic disciplines, beyond just the statistical sciences.*
- *Statistical learning should not be viewed as a series of black boxes.*
- *While it is important to know what job is performed by each cog, it is not necessary to have the skills to construct the machine inside the box!*
- *We presume that the reader is interested in applying statistical learning methods to real-world problems.*
**Organization**
*Chapter 2*: Introduces basic terminology and concepts, presents k-nearest neighbors classifier.
*Chapter 3 and 4*: Covers classical linear methods for regression and classification (linear and logistic regression, linear discriminant analysis)
*Chapter 5:* Cross-validation and Bootstrap
*Chapter 6:* Other linear methods; stepwise selection, ridge regression, principal components regression, and the lasso
*Chapter 7:* Single input non linear, additive models.
*Chapter 8:* tree-based methods, bagging, boosting, random forests. 
*Chapter 9:* Support Vector Machines
*Chapter 10:* Deep Learning
*Chapter 11:* Survival Analysis
*Chapter 12:* Unsupervised, input variable but no output. Principal component analysis, k-means clustering, hierarchical clustering.
*Chapter 13:* Multiple Hypothesis Testing
### Chapter 2: Statistical Learning
Suppose that we are statistical consultants hired by a client to
investigate the association between advertising and sales of a particular
product. The Advertising data set consists of the sales of that product
in 200 different markets, along with advertising budgets for the product in
each of those markets for three different media: TV, radio, and newspaper.
In other words, our goal is to develop an accurate model
that can be used to predict sales on the basis of the three media budgets.
In this setting, the advertising budgets are input variables while sales
input is an output variable.
More generally, suppose that we observe a quantitative response Y and p
different predictors, X1 , X2 , . . . , Xp . We assume that there is some
relationship between Y and X = (X1 , X2 , . . . , Xp ), which can be written
in the very general form
Y = f (X) + ε. (2.1)
Here f is some fixed but unknown function of X1 , . . . , Xp , and ε is a random
error term, which is independent of X and has mean zero. In this formula- error term
tion, f represents the systematic information that X provides about Y .
### Chapter 3: Linear Regression
Recall the Advertising data from Chapter 2.
Some questions we may want to ask
- Is there a relationship between advertising budget and sales? Our first goal should be to determine whether the data provide evidence of an association between advertising expenditure and sales. If the evidence is weak, then one might argue that no money should be spent on advertising!
- How strong is the relationship between advertising budget and sales? Assuming that there is a relationship between advertising and sales, we would like to know the strength of this relationship. Does knowledge of the advertising budget provide a lot of information about product sales?
- Which media are associated with sales? Are all three media—TV, radio, and newspaper—associated with sales, or are just one or two of the media associated? To answer this question, we must find a way to separate out the individual contribution of each medium to sales when we have spent money on all three media.
- How large is the association between each medium and sales?For every dollar spent on advertising in a particular medium, by what amount will sales increase? How accurately can we predict this amount of increase?
- How accurately can we predict future sales? For any given level of television, radio, or newspaper advertising, what is our prediction for sales, and what is the accuracy of this prediction?
- Is the relationship linear? If there is approximately a straight-line relationship between advertising expenditure in the various media and sales, then linear regression is an appropriate tool. If not, then it may still be possible to trans- form the predictor or the response so that linear regression can be used.
- Is there synergy among the advertising media? Perhaps spending $50,000 on television advertising and $50,000 on radio advertising is associated with higher sales than allocating $100,000 to either television or radio individually. In marketing, this is known as a synergy effect, while in statistics it is called an interaction effect.
#### 3.1 Simple Linear Regression
Assume there is a linear relationship between X and Y.
 => Y ≈ β0 + β1 X
 In our sales problem, sales ≈ β0 + β1 × TV
β0 and β1 are two unknown constants that represent the intercept and slope terms in the linear model. Together, β0 and β1 are intercept known as the model coefficients or parameters. Once we have used our slope training data to produce estimates β̂0 and β̂1 for the model coefficients, we coefficient can predict future sales on the basis of a particular value of TV advertising parameter by computing
ŷ = β̂0 + β̂1 x,
where ŷ indicates a prediction of Y on the basis of X = x. Here we use a hat symbol, ˆ , to denote the estimated value for an unknown parameter or coefficient, or to denote the predicted value of the response.
##### 3.1.1 Estimating the Coefficients
In practice, β0 and β1 are unknown. So before we can use (3.1) to make
predictions, we must use data to estimate the coefficients. Let
(x1 , y1 ), (x2 , y2 ), . . . , (xn , yn )
represent n observation pairs, each of which consists of X and a measurement of Y.
Let ŷi = β̂0 + β̂1 xi be the prediction for Y based on the ith value of X.
Then ei = yi − ŷi represents the ith residual—this is the difference between
residual the ith observed response value and the ith response value that is predicted
by our linear model. We define the residual sum of squares (RSS) as
or equivalently as
RSS = e21 + e22 + · · · + e2n ,
RSS = (y1 − β̂0 − β̂1 x1 )2 + (y2 − β̂0 − β̂1 x2 )2 + · · · + (yn − β̂0 − β̂1 xn )2 . (3.3)