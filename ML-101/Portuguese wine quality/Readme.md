# Wine Quality.

## Ranking of Portuguese White Wines by Quality.

Toolset: Logistic Regression & KNN & Decision Tree comparison  
with hyperparameters  
with over/under-sampling  

## Table of Contents

### Introduction: Data set Overview
The dataset that's we see here contains 12 columns and 4898 entries of data about Portuguese white wines.
    
**Properties:**
    
* **fixed acidity**  
* **volatile acidity**  
* **citric acid**  
* **residual sugar**  
* **chlorides**  
* **free sulfur dioxide**  
* **total sulfur dioxide**  
* **density**  
* **pH**  
* **sulphates**  
* **alcohol**  
* **quality** - score between 3 and 9  

### Questions:
    
Predict which wines are 'Good/1' and 'Not Good/0' (binary classification; check balance of classes; save predictions to .csv)


## [Part 1: Import, Load Data](./Wine%20quality%20-%20Classification.ipynb#Comclusion)
* ### Import libraries, Read data from ‘.csv’ file

## [Part 2: Exploratory Data Analysis](Wine%20quality%20-%20Classification.ipynb#Part-2-Exploratory-Data-Analysis)
* ### Info, Head, Describe
* ### Encoding 'quality' attribute
* ### 'quality' attribute value counts and visualisation
* ### Resampling of an imbalanced dataset
* ### Random under-sampling of an imbalanced dataset
* ### Random over-sampling of an imbalanced dataset
* ### Initialisation of target
* ### Drop column 'quality'

## [Part 3: Data Wrangling and Transformation](Wine%20quality%20-%20Classification.ipynb#part-3-data-wrangling-and-transformation)  
* ### StandardScaler
* ### Creating datasets for ML part
* ### 'Train\Test' splitting method

## [Part 4: Machine Learning](Wine%20quality%20-%20Classification.ipynb#Part-4-Machine-Learning)
* ### Build, train and evaluate models without hyperparameters
    * #### Logistic Regression, K-Nearest Neighbors, Decision Trees 
    * #### Classification report
    * #### Confusion Matrix
    * #### ROC-AUC score
* ### Build, train and evaluate models with hyperparameters
    * #### Logistic Regression, K-Nearest Neighbors, Decision Trees 
    * #### Classification report
    * #### Confusion Matrix
    * #### ROC-AUC score

## [Conclusion](Wine%20quality%20-%20Classification.ipynb#conclusion)

