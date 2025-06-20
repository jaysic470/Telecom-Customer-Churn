# Telecom Customer Churn Prediction - [Notebook](https://github.com/jaysic470/Telecom-Customer-Churn/blob/main/Telecom-Customer-Churn.ipynb)

This project aims to predict customer churn for a telecommunications company using machine learning. Early identification of customers likely to leave enables proactive retention strategies, saving the business money and improving long-term customer satisfaction.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Data Description](#data-description)
- [Business Objective](#business-objective)
- [Process Summary](#process-summary)
- [Modeling & Results](#modeling--results)
- [Business Recommendations](#business-recommendations)
- [Tools Used](#tools-used)
- [Project Structure](#project-structure)

---

## Project Overview

Churn is a major concern for subscription-based businesses like telecom providers. In this project, we built a predictive model that identifies customers at risk of churning based on their demographics, account details, services, and billing behavior.

The full data science pipeline was applied:
- Merging multiple datasets
- Data cleaning and preprocessing
- Exploratory analysis
- Feature engineering
- Model training, tuning, and evaluation

---

## Data Description

The project uses four datasets:
- `contract.csv`: contract types and billing information
- `internet.csv`: internet services used
- `personal.csv`: customer demographics
- `phone.csv`: phone service details

All datasets were merged using a common `customerID` field.

The target variable is:
EndDate != 'No' → churned (1)
EndDate == 'No' → active (0)

---

## Business Objective

The goal is to identify customers likely to churn so the company can:
- Offer retention deals
- Target support to high-risk customers
- Reduce customer acquisition costs

---

## Process Summary

1. **Data Preparation**
   - Merged four datasets into one clean dataframe
   - Addressed missing values and inconsistent entries
   - Converted dates and engineered target variable

2. **Exploratory Data Analysis**
   - Analyzed churn trends by contract type, payment method, services used, and demographics
   - Identified key churn drivers: monthly charges, contract type, internet service

3. **Feature Engineering**
   - One-hot encoded categorical variables
   - Removed highly correlated and low-variance features

4. **Modeling**
   - Trained and evaluated: Logistic Regression, Random Forest, LightGBM, and XGBoost
   - Used cross-validation and ROC-AUC as primary metric

---

## Modeling & Results

- **Best model**: XGBoost
- **Evaluation Metrics**:
  - ROC-AUC: ~0.87
  - Accuracy: ~80%
- Logistic Regression performed well and offered interpretability.
- Feature importance showed `contract type` and `monthly charges` were top predictors.

---

## Business Recommendations

- Target **month-to-month** customers with loyalty incentives
- Monitor **high monthly charge** accounts and offer custom billing support
- Streamline **online service offerings** and reduce service-related friction

---

## Tools Used

- Python: `pandas`, `NumPy`, `scikit-learn`, `xgboost`, `lightgbm`
- Visualization: `matplotlib`, `seaborn`
- Modeling: Classification models, GridSearchCV, ROC-AUC scoring

---

## Project Structure
Telecom-Customer-Churn/
├── Telecom-Customer-Churn.ipynb # Full analysis and modeling notebook
├── README.md # Project overview and summary
├── datasets/ # Raw input data
└── final_provider
├── contract.csv
├── internet.csv
├── personal.csv
├── phone.csv
