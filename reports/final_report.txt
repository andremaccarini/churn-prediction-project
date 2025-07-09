# Customer Churn Prediction — Final Report

## Objective
This project aims to predict customer churn using historical data from a financial institution. The goal is to identify which clients are most likely to leave and what factors contribute to that decision.

---

## Dataset
- Total records: **10,000**
- Features: **CreditScore, Age, Balance, Tenure, etc.**
- Target: **Exited** (1 if the customer left, 0 otherwise)

---

## Data Cleaning & EDA
- **Missing values:** Present in `Tenure`, filled with median.
- **Target imbalance:** ~20% churn rate — justified the use of F1-score and ROC-AUC.
- **Notable patterns:**
  - `IsActiveMember`: Negative correlation with churn (inactive clients leave more).
  - `Age`: Weak direct correlation, but stronger when grouped.
  - `Gender`: Women churn more (25.1% vs. 19.5%).
  - `Geography`: German customers have higher churn rate.

---

## Feature Engineering
Created new features to capture behavioral patterns:
- `IsWealthy`: Clients with both high balance and salary.
- `OneProductCustomer`: Clients with only one product and no credit card.
- `BalanceSalaryRatio`: Balance divided by estimated salary.
- Encoded categorical variables using `get_dummies`.

---

## Modeling & Evaluation

Three algorithms tested:
- `Random Forest`
- `Logistic Regression`
- `SVM (SVC)`

Each model was trained in three setups:
- Baseline
- Class-weight balanced
- With undersampling

### Best Performing Model:
**Random Forest with Undersampling**
- **F1 Score:** `0.778`
- **ROC AUC:** `0.859`
- **Best Params:** `{'n_estimators': 200, 'min_samples_split': 5, 'min_samples_leaf': 2, 'max_depth': None}`

### Runner-up:
**SVC with Undersampling**
- **F1 Score:** `0.756`
- **ROC AUC:** `0.846`

---

## Conclusion

- Undersampling helped improve class balance and model performance.
- The final model is reliable for detecting potential churners.
- Further improvements could include:
  - Using SMOTE instead of random undersampling.
  - Deploying the model as an API.
  - Collecting more recent or granular data.

---

## Artifacts
- Trained model: `models/random_forest_undersample.pkl`
- Cleaned dataset: `data/interim/churn_cleaned.csv`
- Feature-engineered dataset: `data/processed/churn_ready.csv`

## Author
**André Maccarini**
[LinkedIn](https://www.linkedin.com/in/amaccarini/) | [GitHub](https://github.com/andremaccarini) | [Medium](https://medium.com/@andremaccarini)