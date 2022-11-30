# ECS 171 Group Project: Red-Wine Quality

## Group members:
Oscar Hernandez, Caroline Li, Mardan Mahmut, Matthew Schulz, Rishi Thakkar

## Data source: 
https://archive.ics.uci.edu/ml/datasets/Wine+Quality (Red wine only)

## Data Features (12 total):
 - fixed acidity
 - volatile acidity
 - citric acid
 - residual sugar
 - chlorides
 - free sulfur dioxide
 - total sulfur dioxide
 - density
 - pH
 - sulfates
 - alcohol
 - quality (score between 0 and 10)

 ## Group Project Abstract

- This data on red wine was gathered in Northern Portugal. It contains physicochemical qualities of wine as well as a subject value on quality ranging from 0-10.  
- We can create a model that uses the physicochemical attributes to determine whether a red wine will be good or not. 
- Then, to determine this we will convert quality values to 1, if they are above a threshold such as 7 or 8, and if they are below convert them to 0. 
- We will then use logistic regression to create a model that can predict quality;furthermore, we can create a correlation matrix and model coefficients on a scatterplot to see which attributes strongly affect the taste of red wine. 
- This model can be used to determine which factors significantly influence the quality of red wine to improve flavor and can help create a guideline on what values each component should have. 
- Also, if the wine were to taste bad, then these attributes could be checked under the model to determine which characteristic is negatively affecting the flavor.
- Another model can be created using polynomial regression, which could determine the attribute with the highest correlation to quality as well.

https://github.com/Apolloscar/ECS171_GroupProject

## Preprocessing & First Model Building Milestone:

### Part 1: Data Preprocessing
- To begin, semi-colons were replaced with commas in our csv file to make the formatting consistent with past homework files we have used before.
- Next, since the data types of all the features were numerical, no data was dropped, and no observations were removed or filled in because there were no NULL values.
- Afterwards, we determined that our data had some outliers, so we made note to utilize MinMax scaling in order to avoid any outliers negatively impacting the data and therefore the model.
- Furthermore, we created a new column named 'target', iterated through the 'quality' column, and populated the 'target' entries with 0 if the element in the 'quality' column was less or equal to the 'quality' median value and 1 otherwise. We then dropped the 'quality' column for the model.
- We noticed the frequency of ones in the 'target' column was much lower than the frequency of zeroes, so we took note to oversample our traning data when building the model. This way there will be enough data on each of the 'target' values to to train the model better. 

### Part 2: First Model Build Using Logistic Regression
- We then began to build our logistic regression model utilizing all the information we collected:
     - We oversampled our training data, scaled using MinMax, and then fitted and ran our model.

#### Model Reports:
 - From the MSE of training and testing, it is observed that the model provided is neither overfitting nor underfitting; training MSE is low and both training MSE and testing MSE are relatively close in value. 
 - From the coefficient scatterplot, it is shown that the feature with the most impact in reaching good quality is alcohol since it has the highest magnitude value. 
