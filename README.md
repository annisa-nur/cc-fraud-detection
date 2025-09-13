# Credit Card Fraud Detection in Imbalanced Data With XGBoost-DNN Model
This model took a reference from literature by reethi Devan and Neelu Khare (2020), "An efficient XGBoost–DNN-based classification model for network intrusion detection system".

## Overview
The surge in digital transactions has heightened the risk of credit card fraud, which is often hidden in highly imbalanced data, making the detection of rare fraudulent cases challenging. This study aims to develop an effective real-time credit card fraud detection system for imbalanced data using an XGBoost-Deep Neural Network (DNN) model. XGBoost is utilized for feature selection and 
complexity reduction, while the DNN is employed to capture complex patterns within the data. Various resampling techniques are applied and their performances are compared using metrics such as recall, precision, F-score, AUC-PR, computational time, and latency. The results reveal two standout models: Model 2 (Random Oversampling with a two-hidden-layers DNN architecture) achieved the highest F2-score of 0,860 at a threshold of 0,5, and Model 7' (SMOTE-Random Undersampling with a three-hidden-layers DNN architecture) achieved the highest recall of 0,908 at a threshold of 0,1. Model 2 is suitable for a balanced approach, whereas Model 7' is ideal for minimizing financial losses from fraud. All top-performing models demonstrated a latency of < 1 m s per transaction, meeting the requirements of a real-time system. These findings provide strategic guidance for banks in selecting a model that aligns with their specific priorities and risk tolerance. 

## Dataset
The dataset used is the European Credit Card Fraud Detection dataset, containing transactions made by credit card holders in September 2013. The dataset includes 284,807 transactions, with 492 frauds, making it highly imbalanced (fraudulent transactions account for 0.172% of the total transactions).

## Key Features:
- V1 to V28: Principal components resulting from a PCA transformation. Due to confidentiality, the original features are not available.
- Time: The time (in seconds) since the first transaction in the dataset.
- Amount: The transaction amount, which can be used in cost-sensitive learning.
- Class: The target variable where 1 represents fraud and 0 represents a non-fraudulent transaction.
- Data Imbalance Handling: Since fraudulent transactions make up a very small portion of the dataset, SMOTE is applied to oversample the minority class (fraudulent transactions), helping the model learn better by balancing the dataset before training.

## Thesis Paper:
[Thesis Paper](http://repository.ipb.ac.id/handle/123456789/168822)
