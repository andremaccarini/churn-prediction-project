# Customer Churn Prediction

## Project Overview

This project applies data analysis and machine learning to predict customer churn using a dataset provided by TripleTen. The workflow follows a structured pipeline — from exploratory data analysis (EDA) to feature engineering, model evaluation, and final reporting.

It aims to identify patterns related to customer attrition and to assist businesses in anticipating which customers are at risk of leaving.

##  Project Structure

churn-prediction-project/
├── data/
│ ├── raw/ # Original data
│ ├── interim/ # Cleaned data
│ └── processed/ # Data ready for modeling
├── models/ # Trained model (.pkl)
├── notebooks/ # Jupyter notebooks (EDA, features, modeling)
├── reports/
│ ├── figures/ # Visualizations from notebooks
│ └── final_report.md
├── requirements.txt
└── README.md

## 🔄 Workflow Summary

1. **EDA**: Investigated data quality, correlation analysis, missing value handling.
2. **Feature Engineering**: Created new features such as `AgeGroup`, `BalanceSalaryRatio`, and `IsWealthy`. Applied one-hot encoding and scaling.
3. **Modeling**: Compared multiple models:
   - Random Forest
   - Logistic Regression
   - Support Vector Classifier
   All models were evaluated with and without undersampling.
4. **Evaluation Metrics**:
   - F1 Score
   - ROC AUC
   - Confusion Matrix
   - ROC Curve

---

##  Best Model

The best-performing model was **Random Forest with undersampling**, achieving:

- F1 Score: **0.778**
- ROC AUC: **0.859**

This model was saved in the `/models/` folder and can be used for deployment or future testing.

---

##  Key Findings

- Churn rate was highly imbalanced (≈20%).
- `IsActiveMember`, `Age`, and `Geography_Germany` had the strongest association with churn.
- Customers with no balance and only one product showed slightly higher churn risk.
- Undersampling significantly improved model performance.

---

##  Visual Insights

All key visualizations from the notebooks (correlation heatmaps, ROC curves, churn by feature) are saved in `/reports/figures`.

---

##  Next Steps

- Add cross-validation with time series split (if temporal order matters)
- Test additional ensemble models (e.g., XGBoost, LightGBM)
- Deploy the model using Streamlit or Flask

---

##  Author

André Maccarini 
🔗 [LinkedIn](https://www.linkedin.com/in/amaccarini/) • [Medium](https://medium.com/@andremaccarini) • [Github](https://github.com/andremaccarini)

---

##  License

This project is licensed under the MIT License.