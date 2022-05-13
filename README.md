# Project Overview
This project repository is created in partial fulfillment of the requirements for the Predictive Analytics course offered by the Master of Science in Business Analytics program at the Carlson School of Management, University of Minnesota.

## Key Question
How can we predict if a Sanatander customer will make a transaction in future based on 200 anonymized features?

## Topic
Santander is a Spanish multinational corporation bank and financial-based company operating in Europe, Asia, and North and South America. Santander continually helps its customers:
- understand their financial health
- discern products and services helpful for achieving their monetary goals
In this scenario, we want to identify customers who will make a transaction in the future, irrespective of the amount of money transacted. Some examples of transaction include drawing out money from ATM, writing a cheque, depositing money in bank and so on and so forth.


## Dataset
Our data is from a kaggle competition It is completely anonymized, i.e. the features/variables have no names. Dataset with
- 200 features
- 200,000 records 
- Binary variable for transaction occurrence:
    0: No Transaction
    1: Transaction

90% customers have no transaction. There are no missing values in the dataset. All features are numeric.

Data Source Link: https://www.kaggle.com/competitions/santander-customer-transaction-prediction

## Approach
- EDA is performed by checking data distribution and correlation analysis.
- Repetition of similar values is observed in almost all columns of the dataset. Hence, feature engineering is done. Data point is flagged “Real” if at least 1 feature value is  unique in its own column
- Extra column is added for every feature containing the value's corrsponding real/fake flag(0/1)
- Models such as XGBoost, LightGBM and deep neural networks are tried, rendering average results
- Basic models mentioned in the previous step are stacked together. This is followed by ensembling 200 models, one model for every feature and its flag
- 200 stacking models are then ensembled which achieved best performance, an AUC of 0.916

## Results
91.4% of the time, the model will rank a true purchasing customer ahead of a customer that will not actually purchase. Santander can take strategic business decisions based on this information and approach the diferent sets of customers in separate ways.
