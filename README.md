
# Bank Customer Churn Prediction (GBDT)

## Project Overview
This project builds a machine learning model to predict **customer churn** for a bank.
Customer churn means whether a customer will **leave the bank**.
The goal is to identify high-risk customers using tabular data and interpretable features.

The model is built using **Gradient Boosting Decision Trees (GBDT)** and evaluated with **ROC-AUC**
using stratified cross-validation.

---

## Dataset
The dataset contains anonymized bank customer information, including:
- Credit score
- Age
- Tenure
- Balance
- Number of products
- Customer activity indicators
- Geography and gender (encoded as integers)

**Target variable**
- `Exited`
  - `1` = customer exited
  - `0` = customer stayed

---

## Approach

### 1. Data Preparation
- Removed identifier columns (`id`, `CustomerId`) to prevent data leakage
- Split features (`X`) and target (`y`)
- Ensured consistent features between training and test data

### 2. Feature Engineering
Created simple and interpretable cross-features:
- **SingleProduct**: customer has only one product
- **CardButInactive**: customer has a credit card but is not active
- **ZeroBalance**: account balance is zero

These features capture customer engagement and product usage behavior.

### 3. Model
- **Model**: Gradient Boosting Classifier
- **Reason**: GBDT handles non-linear relationships well and performs strongly on tabular data

### 4. Evaluation
- **Method**: 5-fold Stratified Cross-Validation
- **Metric**: ROC-AUC
- Stratification handles class imbalance correctly

---

## Results
- The model shows **stable ROC-AUC across folds**
- Feature importance analysis indicates that:
  - Age
  - NumOfProducts
  - IsActiveMember
  - SingleProduct
  - Geography
  - Balance
  are strong predictors of churn

---


---

## How to Run
1. Upload the notebook to Kaggle or run locally
2. Make sure `train.csv` and `test.csv` are available
3. Run all notebook cells from top to bottom

The notebook is fully reproducible.

---

## Key Takeaways
- Simple, business-driven features can significantly improve churn prediction
- Tree-based models naturally handle mixed feature types
- Cross-validation is essential for reliable performance estimation

---


## Author
Joy  
Background in data mining and applied machine learning

