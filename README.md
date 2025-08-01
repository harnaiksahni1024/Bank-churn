# 🏦 Bank Customer Data - Exploratory Data Analysis (EDA)

This repository contains an exploratory data analysis (EDA) notebook that analyzes a banking dataset. The goal is to understand customer behavior and trends to inform decision-making for targeted services such as marketing campaigns, product offerings, and customer retention strategies.


## 🔍 Features

- Data cleaning and preprocessing
- Univariate and multivariate analysis
- Correlation and distribution visualization
- Customer segmentation insights
- Target variable behavior analysis

## 📈 Key Insights

Based on the analysis conducted in `bank_eda.ipynb`, here are some major findings:

- **Class Imbalance:** A strong imbalance in the target variable (`y`), with the majority of customers not subscribing to a term deposit.
- **Age Factor:** Older customers (especially above 60) are more likely to subscribe to term deposits.
- **Previous Contacts Matter:** Customers who were previously contacted and had a positive outcome (`poutcome = success`) show a higher likelihood of subscribing again.
- **Contact Type:** Contacting customers via **cellular** phone leads to more subscriptions compared to telephone.
- **Duration Bias:** Longer call duration correlates with higher success, though this is a post-event variable and must be handled carefully in predictive modeling.
- **Job Influence:** Certain professions (e.g., **retired**, **student**) have higher subscription rates compared to blue-collar or unemployed individuals.
- **Education Level:** Customers with higher education levels have slightly higher conversion rates.
- **Month of Contact:** Most conversions occur during the months of **March**, **May**, **August**, and **October**.

> These insights can be used to refine marketing strategies and optimize campaign timing, audience targeting, and communication channels.

## 📊 Key Libraries Used

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `plotly` (optional)
- `scikit-learn` (optional, for clustering or PCA)


This project focuses on building industry-level machine learning models to predict customer churn for a bank. Churn prediction helps businesses proactively identify customers who are likely to leave and take preventive actions.

---

## 📂 Dataset

- **Source**: `resources/analytical_base_table.csv`
- **Target Variable**: `Exited` (1 = churned, 0 = retained)
- **Features**: Demographic and account activity features.

---

## ⚙️ Modeling Approach

- Used **industry-standard ML pipelines** for consistent preprocessing and modeling.
- Applied **Stratified K-Fold Cross-Validation** to ensure balanced class distribution across folds.
- Addressed **class imbalance** using:
  - `class_weight='balanced'` where applicable.
  - Custom **threshold tuning** for each model post-prediction.
- All models were serialized using `joblib` and stored in the `models/` directory.

---

## 🧪 Models Evaluated

| Model                   | Precision | Recall   | F1 (Macro) | Accuracy | ROC AUC  |
|------------------------|-----------|----------|------------|----------|----------|
| Decision Tree          | 0.4974    | 0.6953   | 0.5799     | 0.7950   | 0.8426   |
| K-Nearest Neighbors    | 0.4512    | 0.6241   | 0.5237     | 0.7690   | 0.8020   |
| Logistic Regression    | 0.5130    | 0.6781   | 0.5841     | 0.8035   | 0.8382   |
| Random Forest          | 0.6250    | 0.6143   | 0.6196     | 0.8465   | 0.8618   |
| XGBoost                | 0.6028    | 0.6339   | 0.6180     | 0.8405   | 0.8639   |
| Support Vector Classifier | 0.5948 | 0.6241   | 0.6091     | 0.8370   | 0.8551   |

---

## 🛠️ Technologies Used

- Python
- pandas, numpy
- scikit-learn
- XGBoost
- joblib (for saving models)

---

## 🧮 Evaluation Metrics

- **Precision**: Fraction of true churn predictions out of all churn predictions.
- **Recall**: Fraction of actual churners identified.
- **F1 Macro**: Harmonic mean of precision and recall across both classes.
- **Accuracy**: Overall correct predictions.
- **ROC AUC**: Model’s ability to distinguish churners vs. non-churners.

---




