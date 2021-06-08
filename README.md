# <p align="center">HR analytics job change of data scientists</p> 

<p align="center">
  <img src=https://img.golos.io/proxy/http://lk.aldmi.ru/wp-content/uploads/2016/04/Divider_03-1.png width="1000" height="100">
</p>

## Problem formulation

*<p align="justify">The company wants to hire data scientists from among people who successfully complete some of the courses the company runs. Many people sign up for their training. The company wants to know which of these candidates really wants to work for the company after training or will be looking for another job. It let to reduce costs and time for training or course planning.</p>*

*The original assignment is at [link](https://www.kaggle.com/arashnic/hr-analytics-job-change-of-data-scientists)*

## Dataset
*<p align="justify">Dataset contains contains information about gender, city, work experience and education from 21000 unique users, which they provide when registering for company courses.</p>*

## Solution description

*To solve this problem a binary classification problem is considered. As seen in Figure 1, the target variable classes are unbalanced.*

<p align="center">
  <img src=pictures/target_balance.png?raw=true "Target Class Balance" width="400" height="600">
</p>

<p align="center">Fig. 1 Target class balance (0 – Not looking for job change, 1 – Looking for a job change)</p> 
                
*<p align="justify">Also some features have from 0% to 40% missing values, that imposes additional conditions to prepare data and tune models.</p>*

### Models
*<p align="justify">Models are used in the project: CatBoostClassifier, RandomForestClassifier and VotingClassifier (based on LGBMClassifier, KNNClassifier and LogisticRegression). Taking into account the above-described issues, in addition to tuning the main hyperparameters of models, various combinations of imputation values and data recovery strategies are also considered. Automation of the parameters selection for these operations is achieved by GridSearchCV using ColumnTransformer and Pipeline constructors.</p>* 

### Metrics
*<p align="justify">Base metric for making choice of the best parameters for each of the models in conditions of class imbalance is "balanced accuracy score". The following metrics are also used for the final comparison of models (Figure 2).</p>*

<p align="center">
  <img src=pictures/metrics.png?raw=true "Metrics" width="200" height="200">
</p>
<p align="center">Fig. 2 Сomparative metrics </p> 
