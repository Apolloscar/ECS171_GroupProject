# ECS171_GroupProject
ECS171 - Group Project Abstract
 
Group members:
Oscar Hernandez, Caroline Li, Mardan Mahmut, Matthew Schulz, Rishi Thakkar

Data source: https://archive.ics.uci.edu/ml/datasets/Wine+Quality 
(Red wine only)

Data Features :
1 - fixed acidity
2 - volatile acidity
3 - citric acid
4 - residual sugar
5 - chlorides
6 - free sulfur dioxide
7 - total sulfur dioxide
8 - density
9 - pH
10 - sulfates
11 - alcohol
12 - quality (score between 0 and 10)

This data on red wine was gathered in Northern Portugal. It contains physicochemical qualities of wine as well as a subject value on quality ranging from 0-10.  We can create a model that uses the physicochemical attributes to determine whether a red wine will be good or not. 
To determine whether or not wine is good we will convert quality values to 1 if they are above a threshold such as 7 or 8, and if they are below convert them to 0. We will then use logistic regression to create a model that can predict quality. Furthermore, we can create a correlation matrix and model coefficients on a scatterplot to see which attributes strongly affect the taste of red wine. 
This model can be used to determine which factors significantly influence the quality of red wine to improve flavor and can help create a guideline on what values each component should have. Also, if the wine were to taste bad, then these attributes could be checked under the model to determine which characteristic is negatively affecting the flavor. Another model can be created using polynomial regression, which could determine the attribute with the highest correlation to quality as well.

https://github.com/Apolloscar/ECS171_GroupProject

First Model:

No observations were removed due to lack of N/A values. Also, all features were kept for the logisict regression model because they were all numerical. However, quality was dropped for the model, and replaced with target that contained 0 if quality was less than the quality median value and 1 otherwise. For scaling, MinMax scaling was used in order to avoid any outliers negatively impacting the data and therefore the model. From the MSE of training and testing, it is observed that the model provided is neither overfitting nor underfitting; training MSE is low and both trainingg MSE and testing MSE are relatively close in value. From the coefficient scatterplot, it is shown that the feature with the most impact in reaching good quality is alcohol since it has the highest magnitude value. 
