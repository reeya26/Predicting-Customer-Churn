# Predicting Customer Churn

The goal is to predict whether the customer of a Telco provider will Churn or not. 

### Dataset

The training dataset contains 4250 samples. Each sample contains 19 features and 1 boolean variable "churn" which indicates the class of the sample.

### Feature Engineering

1. This dataset does not contain any missing values
2. It has a few categorical variables like "Churn" which contain binary values. We have converted them to numerical values by maping it to 1s and 0s.
3. For the other categorical variables, we have used One Hot Encoding to convert them into Numerical variables.
4. There is a _**class imbalance**_ in the Churn values, with only 15% customers being churned. We have used SMOTE to handle the class imbalance. (Synthetic Minority Over-sampling Technique works by creating synthetic (not duplicate) samples from the minority class)

### Methodology 

We have compared two models: Random Forest Classifier and XGBoost Classifier. 
Both of these models are known to handle class imbalance well. I have focused on evaluating the models on two metrics - **Accuracy and Recall**. The cost of re-acquiring a churned customer is higher than the cost giving incentives to an existing customer, hence we want to minimize False Negatives in this scenario. 

### Results

n_estimators = 500

| Metric         | Random Forest |  XGBoost  |
|----------------|---------------|-----------|
| Accuracy       |   95.73 %     |  97.35 %  |
| Recall         |   93.31 %     |  96.02 %  |
| F1 Score       |   95.53 %     |  97.25 %  |


n_estimators = 100

| Metric         | Random Forest |  XGBoost  |
|----------------|---------------|-----------|
| Accuracy       |   95.35 %     |  94.82 %  |
| Recall         |   92.54 %     |  91.44 %  |
| F1 Score       |   95.12 %     |  94.52  %  |




