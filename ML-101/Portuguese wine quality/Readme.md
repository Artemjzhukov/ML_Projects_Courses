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

Сравнительные результаты моделей
Логистическая регрессия показала accuracy 79.1% до оптимизации и 79.2% после, с незначительным изменением ROC-AUC с 0.687 до 0.690. Модель демонстрирует высокую точность для класса 0 (precision 0.816) при низком recall для класса 1 (0.245), что указывает на трудности с идентификацией позитивных случаев.

KNN сохранил стабильные показатели до и после оптимизации: accuracy 83.8%, ROC-AUC 0.770. Модель показывает сбалансированные метрики для обоих классов с precision 0.874 для класса 0 и 0.667 для класса 1.

Дисбаланс метрик (логистическая регрессия):

Класс 0: precision 81.6% (хорошо)  
Класс 1: precision 56.4% (плохо)

Сбалансированные метрики (KNN):

Класс 0: precision 87.4% (хорошо)  
Класс 1: precision 66.7% (нормально)

Сбалансированность означает, что модель одинаково хорошо работает с обоими классами, а не жертвует одним ради другого.

Дерево решений до оптимизации достигло accuracy 84.7% с ROC-AUC 0.779, но после настройки гиперпараметров показало снижение до accuracy 82.9% и ROC-AUC 0.755. Оптимизация привела к уменьшению precision для класса 1 с 0.662 до 0.645.
Precision = "сколько из найденных объектов действительно правильные"
Это значит: когда модель говорит "это класс 1", она теперь ошибается чаще - 35.5% случаев вместо 33.8%.

Основная проблема - все модели плохо справляются с классом 1, что видно по низкому recall (25-53%).

Анализ эффективности оптимизации (низкая)
Настройка гиперпараметров через GridCV не привела к значительному улучшению качества моделей. Логистическая регрессия получила минимальное улучшение, KNN сохранил прежние показатели, а дерево решений показало снижение производительности. 

Почему оптимизация не сработала  
GridSearchCV подобрал параметры, но они не улучшили модели. Возможные причины:

Данные уже хорошо разделяются базовыми настройками  
Параметры были подобраны не оптимально  
Не хватает данных для существенного улучшения

Рекомендации по улучшению
Для повышения качества классификации можно рассмотреть ансамблевые методы, такие как случайный лес или градиентный бустинг, которые часто показывают лучшие результаты на несбалансированных данных. Дополнительная работа с признаками, включая отбор и создание новых переменных, может улучшить идентификацию класса 1. Для логистической регрессии стоит экспериментировать с техниками балансировки классов через class_weight или методы семплирования.

# Результаты оптимизации:

### Лучше всего Random Forest (с балансировкой классов):

БЫЛО (несбалансированная модель):

Accuracy: 85.9% → 89.1% (+3.2%)

Recall класса 1: 48.6% → 68.1% (+19.5%!)

F1 класса 1: 60.3% → 73.3% (+13%)

Confusion Matrix сравнение:

БЫЛО:                          СТАЛО:
[[737  27]                    [[726  38]
 [111 105]]                    [ 69 147]]
 
False Negative: 111 → 69 (-42)  - значительно лучше!
False Positive: 27 → 38 (+11)   - небольшой рост

## Еще опробовано:
Gradient Boosting, Ансамбли

### Вывод:  
Разнообразный ансамбль провалился - добавление большего количества моделей без тщательного отбора и настройки весов привело к ухудшению качества.

### Лучший подход: Вернуться к простому Random Forest с балансировкой классов, который показал наилучшие результаты.

## Что можно было бы еще попробовать: 

SHAP  
SMOTE (Synthetic Minority Oversampling) для линейных моделей например в пайплайне