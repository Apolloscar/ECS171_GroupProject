# ECS 171 Group Project: Red-Wine Quality

## Group members:
Oscar Hernandez, Caroline Li, Mardan Mahmut, Matthew Schulz, Rishi Thakkar

## 1. Introduction
[Data Source](https://archive.ics.uci.edu/ml/datasets/Wine+Quality) (Red wine only)

### Data Features (12 total):
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

 ### Group Project Abstract
- This data on red wine was gathered in Northern Portugal. It contains physicochemical qualities of wine as well as a subject value on quality ranging from 0-10.  
- We can create a model that uses the physicochemical attributes to determine whether a red wine will be good or not. 
- Then, to determine this we will convert quality values to 1, if they are above a threshold such as 7 or 8, and if they are below convert them to 0. 
- We will then use logistic regression to create a model that can predict quality;furthermore, we can create a correlation matrix and model coefficients on a scatterplot to see which attributes strongly affect the taste of red wine. 
- This model can be used to determine which factors significantly influence the quality of red wine to improve flavor and can help create a guideline on what values each component should have. 
- Also, if the wine were to taste bad, then these attributes could be checked under the model to determine which characteristic is negatively affecting the flavor.
- Another model can be created using KNN, which could be used to classify wine as either good or bad with the given features.

## 2. Submission History
  - ToDo

## 3. Code Uploaded
  - [Link to full ipynb on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Project.ipynb)
  - [Link to Data Exploration on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/DataExploration.ipynb)
  - [Link to Preprocessing on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/DataPreprocessing.ipynb)
  - [Link to Model 1 on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/Model1_Logistic.ipynb)
  - [Link to Model 2 on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/Model2_KNN.ipynb)

## 4. Write Up
### A. Introduction
  - We chose to build a project around determining the main factors contributing to a red-wine's quality because we wanted to relate what we learned in class to something completely unrelated. We wanted to show the versatility of topics that machine learning can be applied to. If we can build a model to effectively predict red-wine quality based on its physicochemical attributes, then we can determine the qualities that heavily influence the grade of red-wine. This information can then be used in industry to allow producers to focus on fine tuning attributes, which will produce the highest quality product, and as a result increase the price at which they can sell their red-wine.

### B. Figures
  - ToDo

### C. Methods
-  [Link to full ipynb on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Project.ipynb)

  #### Data Exploration
   - [Link to Data Exploration on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/DataExploration.ipynb)
   - To explore our dataset we executed the following:
     - Printed the data type of each column in our dataframe.
     - Checked if any of the features had missing values.
     - Used the describe() function and created a pairplot.
     - Generated a correlation matrix in the form of a heatmap.



   #### Preprocessing
   - [Link to Preprocessing on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/DataPreprocessing.ipynb)
   - First, we created a new column named **target**, iterated through the **quality** column, and populated the **target** entries with 0 if the element in the **quality** column was less or equal to **quality**'s median value and 1 otherwise. 
   - We then dropped the **quality** column and added **target** to the dataframe. 
   - Finally, we oversampled the **target** data, and utilized MinMax to scale.
   #### Model 1: Logistic Regression
   - [Link to Model 1 on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/Model1_Logistic.ipynb)
   - For our first model, we built it using logistic regression.
   - Used resampled, scaled data to train model.
   - Used model to predict yhat of both training and testing data.
   - Used those values to produce MSE as well as their classification report.
   - Created a scatterplot with coefficients from model and printed their values.

   #### Model 2: KNN Classification
   - [Link to Model 2 on GitHub](https://github.com/Apolloscar/ECS171_GroupProject/blob/main/Code_Sections/Model2_KNN.ipynb)
   - Second model, KNN was used to clasify wine as either good or bad.
   - Test models with different K values and aved their acurracy.
   - Chose K with highest accuracy and used it for model.
   - Predicted yhat for both training and testing data.
   - Calculated MSE and Classification Report with these values.

### D. Results
#### Model 1: Logistic Regression
   
   - From the MSE of training and testing, it is observed that the model provided is neither overfitting nor underfitting; training MSE is low and both training MSE and testing MSE are relatively close in value.

| Data      | MSE     |
| --------  | ------  |
| Training  | 0.1823  |
| Testing   | 0.225   |

   - From the coefficient scatterplot, it is shown that the feature with the most impact in reaching good quality is alcohol since it has the highest magnitude value. 

| Features              | Coefficients  |
| -----------           | -----------   |
| Fixed Acidity         | 2.40104666    |
| Volatile Acidity      | -4.01183912   |
| Citric Acid           | 0.33981768    |
| Residual Sugar        | 1.16270763    |
| Chlorides             | -2.62511007   |
| Free Sulfur Dioxide   | 0.07871166    |
| Total Sulfur Dioxide  | -4.31185535   |
| Density               | -2.12932732   |
| pH                    | 0.04099653    |
| Sulphates             | 4.69369245    |
| Alcohol               | 5.68847506    |

 #### Model 2: KNN Classification
   
   - Trying odd values with 21 and 61, it was determined that a K value of 39 gave us the most accurate model.
   - Given the MSE from training and testing of the model, it is believed that the model is slightly overfitting due to training MSE being low and testing MSE being relatively high.

| Data      | MSE     |
| --------  | ------  |
| Training  | 0.157   |
| Testing   | 0.290   |

 #### Final Results Summary
   - ToDo

### E. Discussion
  - ToDo (Some notes below, see final submission assignment on canvas for more details)

  - As a result of our exploration, we determined that no data needed to be dropped since all of the features were of the same data type, and no observations needed to be removed because no data was NULL. Furthermore, by utilizing the information from the describe() function and the pairplot, we determined that our data had some outliers.
  - We then noticed the frequency of ones in the **target** column was much lower than the frequency of zeroes. To address this, we oversampled our traning data before building the model, so enough data was present in each of the **target** classes to better train the model.
  - to remove the outliers we detected during data exploration.
  - to see how our data was distributed
  #### Model 1: Logistic Regression
  - We wanted to figure out which of the features given in the data had the most impact in affecting the quality of wine. For that reason, logistic regression was used in order to get the coefficients for each feature from the model. After the model we deduced that alcohol was the biggest contributor in quality since it had the highest coefficient. This makes sense with alcohol being the most reviewed feature of wine by consumers. As compared to residual sugar and citric acid, more often than not, a consumer will mostly just check the amount of alcohol in wine. 
  - As for the credibility of this model, it is best to not fully trust it but rather to be taken into consideration. Just because alcohol has the best impact on quality, does not mean that more alcohol will guarantee better quality since there is a limit to how much a human can consume. Also data had limited ranges such as with quality only having values from 3-8, giving us a small amount of good quality wine data. This lack of variety made it harder for the model to be able to predict values outside this range. 
  
  #### Model 2: KNN Classification
  - We wanted to figure out whether or not the quality of the wine was good or bad, therefore we decided to use KNN classification. After testing out different k values between the range of 21 to 61, we found that the k value of 39 gave use the most accurate model. With our resulting model with K = 39, we found the model to be slightly overfitting in part by the low training MSE and the relatively high testing MSE. However, the model supported the findings from the first model that alcohol was the best indicator of a wines quality.
  - The credibility of this model, similarly to model 1, should be taken with a grain of salt. Correlation is not causation, as just because the alcohol level is higher in a wine this will not make its quality better as there is a limit to how high a level of alcohol humans can tolerate. Also other factors such as the aging process, length of aging, and types of wooden barrel used to age the wine can affect the alcohol level, which may be better indicators of wine quality that are not seen in our dataset.
  

### F. Conclusion
  - ToDo

### G. Collaboration
  - ToDo
