# Customer Churn Prediction with Machine Learning

## 📌 Project Overview

Customer churn is a critical problem for many businesses. 
Retaining existing customers is often more cost-effective than acquiring new ones.

This project aims to predict whether a customer will leave (churn) using machine learning techniques.

---

## 📊 Dataset

The dataset contains customer information such as:

- Age
- Balance
- Number of Products
- Credit Card status
- Activity status

Target variable:
- **Exited (1 = churn, 0 = stay)**

---


# README:

# Customer Churn Prediction using Gradient Boosting Ensemble

This notebook focuses on predicting customer churn using multiple Gradient Boosting Decision Tree (GBDT) models and ensemble learning techniques. The project includes data preprocessing, feature engineering, feature importance analysis, model evaluation, and weighted soft-voting ensemble methods.

The final solution combines:
- GradientBoostingClassifier
- XGBoost
- LightGBM

using a weighted ensemble strategy to improve overall ROC-AUC performance.

---

## Project Workflow

### 1. Data Preprocessing
- Missing value handling
- Label encoding for categorical features
- Feature scaling techniques
- Train-validation split

### 2. Feature Engineering
Several feature engineering techniques were applied, including:
- Frequency-based features
- Categorical encoding
- Distribution difference checking between train and test datasets
- Feature importance analysis

Special attention was given to high-cardinality categorical features such as `Surname`, because train-test distribution drift may cause overfitting.

### 3. Model Training
Three tree-based boosting models were trained:

- GradientBoostingClassifier
- XGBoost Classifier
- LightGBM Classifier

Each model was evaluated independently using:
- ROC-AUC
- Validation metrics
- Binary classification evaluation

### 4. Ensemble Learning
A weighted soft-voting ensemble was used to combine model probabilities:

```python
pred_avg = (
    0.4 * y_pred1 +
    0.34 * y_pred2 +
    0.26 * y_pred3
)
```


###  Feature Importance Comparison

Feature importance scores from all three models were compared to analyze:

Shared important features
Model-specific patterns
Potential overfitting risks
Evaluation Metric

### The primary evaluation metric is:

ROC-AUC Score

because churn prediction is a binary classification problem with probability-based evaluation.

### Key Techniques Used
Gradient Boosting Decision Trees (GBDT)
Weighted Soft Voting Ensemble
Feature Scaling
Feature Importance Analysis
Distribution Shift Detection

### Conclusion

This notebook demonstrates how combining multiple boosting models through weighted ensemble learning can improve churn prediction performance. It also highlights the importance of analyzing feature distribution differences and avoiding overfitting caused by high-cardinality categorical variables.

The final ensemble achieved stronger and more stable ROC-AUC performance compared with individual models.





