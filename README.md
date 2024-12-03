# Credit Card Fraud Detection in Imbalanced Data With XGBoost-DNN Model
This model took a reference from literature by reethi Devan and Neelu Khare (2020), "An efficient XGBoost–DNN-based classification model for network intrusion detection system".

## Overview
This repository contains a credit card fraud detection model built using XGBoost for feature selection and Deep Neural Networks (DNN) for classification. The project focuses on addressing class imbalance using SMOTE (Synthetic Minority Over-sampling Technique). The goal of the project is to build an efficient fraud detection system by selecting important features and optimizing the DNN model through hyperparameter tuning and cross-validation.

## Dataset
The dataset used is the European Credit Card Fraud Detection dataset, containing transactions made by credit card holders in September 2013. The dataset includes 284,807 transactions, with 492 frauds, making it highly imbalanced (fraudulent transactions account for 0.172% of the total transactions).

## Key Features:
- V1 to V28: Principal components resulting from a PCA transformation. Due to confidentiality, the original features are not available.
- Time: The time (in seconds) since the first transaction in the dataset.
- Amount: The transaction amount, which can be used in cost-sensitive learning.
- Class: The target variable where 1 represents fraud and 0 represents a non-fraudulent transaction.
- Data Imbalance Handling: Since fraudulent transactions make up a very small portion of the dataset, SMOTE is applied to oversample the minority class (fraudulent transactions), helping the model learn better by balancing the dataset before training.

## Methodology
1. Data Preprocessing:
Sampling: A 3% sample of the dataset is taken from both the fraud and non-fraud categories to minimize testing time while preserving the class distribution.
Normalization: The Time and Amount features are normalized, as they are the only non-transformed features in the dataset.
SMOTE: Used to balance the dataset by oversampling the minority (fraudulent) class.
2. Feature Selection:
XGBoost is first used to perform feature selection based on feature importance scores. The top features are selected to reduce dimensionality and improve the performance of the model.
3. Model Development:
Deep Neural Network (DNN) is then trained using the selected features. The model is optimized using the Adam optimizer with an initial learning rate of 0.01.
Hyperparameter Tuning: The model undergoes hyperparameter tuning to find the optimal parameters for training.
Stratified K-Fold Cross-Validation: Given the imbalanced nature of the dataset, stratified k-fold cross-validation is used to ensure that both classes are represented proportionally in each fold.
4. Model Evaluation:
The model’s performance is evaluated using various metrics such as accuracy, precision, recall, and F1-score.
Final Results:
Accuracy: 99%
Precision: 0.75
Recall: 1.00
F1-Score: 0.85
These results indicate that the model works well, with high sensitivity to detect fraudulent transactions, while maintaining a reasonable precision and F1 score.
