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

## ⚙️ Methodology

### 1. Feature Selection
Selected key features that are relevant to customer behavior, including:
- Age
- Balance
- NumOfProducts
- IsActiveMember
- Behavioral indicators (e.g., ZeroBalance)

---

### 2. Customer Segmentation (Clustering)

Applied **KMeans clustering** to group customers into different segments.

👉 Idea:
Different customer groups may have different churn patterns.

---

### 3. Model Training

For each cluster, trained separate models:

- Gradient Boosting Classifier (GBDT)
- XGBoost Classifier

Selected the best-performing model for each cluster.

---

### 4. Model Evaluation

Used **ROC-AUC** as the evaluation metric.

---

## 📈 Results

- **Method**: 5-fold Stratified Cross-Validation
- **Metric**: ROC-AUC
- Stratification handles class imbalance correctly
#### Adjust the decision threshold
- Although adjusting the decision threshold improved **classification accuracy** , manual probability modification degraded AUC due to disruption of global ranking. Therefore, threshold optimization was preferred over probability manipulation. the accuracey is better while the threshold is 0.475
---
Tuning hyperparameters is also an effective way to improve prediction performance. For example: GradientBoostingClassifier(n_estimators=3000,learning_rate=0.02,max_depth=5,subsample=0.8,max_features=0.8,random_state=42)
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


<img width="1586" height="837" alt="image" src="https://github.com/user-attachments/assets/7aa3a96b-c42c-42a2-a76e-7e80ca09e7bd" />

---

## 💡 Key Insights

- Inactive customers are more likely to churn
- Customers with fewer products show higher churn risk
- Behavioral features are more important than demographic features

---

## 🛠 Tools & Technologies

- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib / Seaborn

---

## 🚀 Business Impact

This model can help companies:

- Identify high-risk customers
- Apply targeted retention strategies
- Reduce customer churn rate

---

## 📁 Project Structure

project/
├── data/
├── notebook/
├── README.md


---

## 🔮 Future Work

- Hyperparameter optimization
- Add more feature engineering
- Try LightGBM / Neural Networks
- Deploy model as API

---

## 👤 Author

Le Wang  





