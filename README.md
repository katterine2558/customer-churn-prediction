# Telco Churn ML Pipeline

This repository contains an end-to-end workflow to predict customer churn in telecom using Python and scikit-learn.

**What’s inside**
- Exploratory Data Analysis (EDA)
- Data cleaning and type fixes (`TotalCharges`), One-Hot encoding for categoricals
- Stratified 80/20 train–test split and class imbalance handling (`class_weight`)
- Reproducible pipelines: **Decision Tree** (baseline) and **Random Forest** (advanced)
- Hyperparameter tuning with **GridSearchCV** (refit on F1)
- Evaluation: confusion matrix, F1-score, ROC-AUC, Precision-Recall curves
- Interpretability: global feature importance and local explanations with **LIME**

**How to run**
Open the notebook and execute cells in order. Results include the best models, test metrics, and interpretability plots.
