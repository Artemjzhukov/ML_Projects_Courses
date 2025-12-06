juqw11Classification Portuguese Wines 

## Classification of the Quality of Portuguese White Wines 

Toolset: Logistic Regression & KNN & Decision Tree comparison  
with hyperparameters  
with over/under-sampling  
*after conclusion:* RandomForest, Boosting & Encemles

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


[Part 1: Import, Load Data](./Wine%20quality%20-%20Classification.ipynb#Comclusion)

[Part 2: Exploratory Data Analysis](Wine%20quality%20-%20Classification.ipynb#Part-2-Exploratory-Data-Analysis)

[Part 3: Data Wrangling and Transformation](Wine%20quality%20-%20Classification.ipynb#part-3-data-wrangling-and-transformation)  

[Part 4: Machine Learning](Wine%20quality%20-%20Classification.ipynb#Part-4-Machine-Learning)

[Conclusion](Wine%20quality%20-%20Classification.ipynb#conclusion)

![Final Results/](/Final_results.png)

**The final Ensemble** model proves to be the most robust solution, effectively leveraging the complementary strengths of Gradient Boosting and KNN. 
It *achieves the highest* overall PR-AUC score (~0.833) and F1-score (~0.714), providing the best trade-off between identifying good wines (Recall) and minimizing false positives (Precision).  
The confusion matrix confirms it correctly identifies a significant portion of the minority class while maintaining high accuracy on the majority class.    
This demonstrates the power of ensemble methods in leveraging diverse model predictions to improve overall robustness and accuracy.  
The final model is ready for deployment, with the Voting Classifier being the recommended choice due to its balanced and strong performance across key metrics for our imbalanced classification task.

However, while the **Ensemble** offers peak performance, the **tuned KNN** model remains a compelling alternative due to its simplicity, lower training costs, and ease of deployment.
In contrast, the **Ensemble model**, though more performant, requires maintaining multiple models, more memory, and longer inference times. 

**The final choice** between these models should weigh the marginal performance gains of the Ensemble against  
the increased complexity, training time, and economic costs associated with implementing and maintaining such a sophisticated system.