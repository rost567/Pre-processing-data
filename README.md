We will discuss the step by step approach to create a Machine Learning predictive model for the apt salary band, based on a "Census Income" 32521 professionals from around the world in 2020.  
This flow is iseful to solve any supervised ML classification problem, following Thinking Neuron web site:  

1. Reading the data in python:
2. Defining the problem statement
Create a predictive model which can tell if a person deserves a salary grater than 50,000 dollars or not?
3. Identifying the Target variable
   * Target variable = SalaryGT50K.
   * Predictors =  age, workclass, education, marital_status, occupation, etc.
   * SalaryGT50K = 0, The employe earns less than 50k in a year.
   * SalaryGT50K = 1, The employe earns more than 50k in a year.  

Based on the problem statement we need to create a **supervised ML classification model**, as the target variable is categorical.  
Keeping in mind that for other cases of the Target Variable would be:  
- Continuous, i.e. actual salary amount, the task would be a regression problem and the goal would be to predict a numerical values.
- Time seriesforecasting for temporal data, i.e. predicting salary over time,
- Unsupervised Model for continuos target variable: If the problem did not involve predicting a target vairable, instead to dicover inherent patterns or grouping in the data. 

4. Looking at the distribution of Target variable
The question of the "SalaryGT50K" column is if it is more or less than 50K, only 2 types of responses, 0 or 1.
The data distribution of the target variable is satisfatory to proceed further. There are sufficient number of rows for each category to learn from.
5. Basic Data exploration
6. Rejection useless columns  
7. Visual exploratory Data Analysis
8. Feature Selection based on data distribution.
9. Outlier treatment
  We have below two options to treat outliers in the data.

 > - Option-1: Delete the outlier Records. Only if there are just few rows lost.
 > - Option-2: Impute the outlier values with a logical business value.
10. Missing Values treatment
11. Visual  correlation analysis
12. Statistical correlation analysis (**Feature selection**, sampling)
              ##### ANOVA Resultss ##### 
              
              - age is correlated with SalaryGT50K |P-Value: 0.0
              - fnlwgt is NOT correlated with SalaryGT50K | P-Value: 0.10034099994119691
              - capital_gain is correlated with SalaryGT50K |P-Value: 0.0
              - capital.loss is correlated with SalaryGT50K |P-Value: 4.266838502495211e-143
              - hours_per_week is correlated with SalaryGT50K |P-Value: 0.0
              
              Finally selected continuous variables: ['age', 'capital_gain', 'capital.loss', 'hours_per_week']
              
              ###### CHI-SQUARED TEST ####
              
              - workclass is correlated with SalaryGT50K | P-Value: 3.352256069028484e-220
              - education is correlated with SalaryGT50K | P-Value: 0.0
              - marital_status is correlated with SalaryGT50K | P-Value: 0.0
              - occupation is correlated with SalaryGT50K | P-Value: 0.0
              - relationship is correlated with SalaryGT50K | P-Value: 0.0
              - race is correlated with SalaryGT50K | P-Value: 2.2797874171824478e-70
              - sex is correlated with SalaryGT50K | P-Value: 0.0
              
              Finally selected categorical variables: ['workclass',
               'education',
               'marital_status',
               'occupation',
               'relationship',
               'race',
               'sex']

13. Converting data to numeric for ML
14. K-fold cross validation
    > - **Testing data:** Some data is randomly selected and kept aside for checking how good the model is. Typically 30% of the data is used here.  
    > - **Training data:** The remaining data. On which the model is built. Typically 70% of the data is used here.

15. Trying multiple classification algorithms
16. Selecting the best Model
    After trying multiple classification algorithms, now is time to select the algorithm **with best average accuracy**.
    We have 7 algorithms, here the results:
              1. Logistic Regression 
              > - Accuracy of the model on Testing Sample Data: 0.85
              > - Final Average Accuracy of the model: 0.85
              
              2. Decision Trees
              > - Accuracy of the model on Testing Sample Data: 0.84
              > - Final Average Accuracy of the model: 0.83
              
              3. Random Forest
              > - Acuracy of the model on Testing Sample data: 0.83
              > - Final Average Accuracy of the model:  0.82
                  
              4. AdaBoost
              > - Accuracy of the model on Testing Sample Data: 0.84
              > - Final Average Accuracy of the model: 0.84   
                  
              5. XGBoost 
              > - Accuracy of the model on Testing Sample Data: 0.86
              > - Final Average Accuracy of the model: 0.85
              
              6. KNN _ K-Nearest Neighbor
              > - Accuracy of the model on Testing Sample Data: 0.82
              > - Final average accuracy of the model 0.82
              
              7. SVM_Support Vector Machines
              > - Accuracy of the model on Testing Sample Data: 0.84
              > - Final Average Accuracy of the model: 0.85
                  
              8. Naive Bayes  
              > - Accuracy of the model on Testing Sample Data: 0.64
              > - Final Average Accuracy of the model: 0.63
    
17. Deploying the best model in production -not now- 

