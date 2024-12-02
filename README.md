## Analysing Fraudulent Transactions

# Overview
This project focuses on building a fraud detection system for financial transactions using machine learning. The goal is to predict fraudulent transactions by analyzing various transaction details. The dataset consists of several features, including transaction amount, type, sender and receiver account details, and account balances. The challenge involves detecting fraud in a highly imbalanced dataset, where fraudulent transactions are rare.

![image](https://github.com/user-attachments/assets/a735731a-8c85-4b6e-a7dc-7896c4cf136f)

We used four different strategies for model development:

1. **Two Classical Machine Learning Models**: Logistic Regression and Decision Tree.
2. **Ensemble Model**: Random Forest and XGBoost.
3. **Non-Classical Approach**: Isolation Forest.

Each model was evaluated using performance metrics such as accuracy, precision, recall, F1-score, and ROC-AUC.

# 1. Data Preprocessing and Cleaning

Before developing the models, we performed essential data cleaning tasks:
- **Missing values**: We identified any missing values in the dataset and handled them appropriately, either by filling them with the median (for numerical data) or by using other strategies.
- **Outliers**: We detected and removed outliers using the Interquartile Range (IQR) method to avoid skewing model performance.
- **Feature selection**: We focused on features that are relevant for detecting fraudulent behavior. Features like transaction type, amount, sender/receiver account details, and balance changes were identified as key predictors.
- **Encoding categorical features**: We transformed categorical variables, such as the transaction type and customer names, using one-hot encoding.

# **2. Model Development**

We implemented four distinct approaches to model fraud detection:

- **Classical Models**:
  - **Logistic Regression**: We used Logistic Regression as a baseline model. It is a simple linear classifier that helps understand the relationship between transaction characteristics and fraud.
  - **Decision Tree**: A Decision Tree model was used next. It can capture non-linear relationships between the features and target variable (fraud vs. non-fraud) by recursively splitting the data based on the most informative features.
  
- **Ensemble Models**:
  - **Random Forest**: We trained a Random Forest, an ensemble method that combines the predictions of multiple decision trees to improve model accuracy and reduce overfitting.
  - **XGBoost**: XGBoost was chosen as another ensemble model, known for its high performance and scalability. It applies gradient boosting to iteratively improve weak models, resulting in robust performance, especially in imbalanced datasets like this one.

- **Non-Classical Approach**:
  - **Isolation Forest**: This model is designed to detect anomalies (outliers). Since fraudulent transactions can be considered anomalies, Isolation Forest works by isolating instances in the dataset that deviate from the majority, thus identifying potential frauds.

