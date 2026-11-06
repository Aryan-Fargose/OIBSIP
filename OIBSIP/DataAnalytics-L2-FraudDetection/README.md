
# Credit Card Fraud Detection

## OIBSIP – Data Analytics Internship | Level 2 – Task 3

### Project Overview

This project focuses on detecting fraudulent credit card transactions using Machine Learning classification techniques.

The objective is to identify suspicious transactions from a highly imbalanced dataset and evaluate the performance of different classification models.

Two machine learning algorithms were implemented:
- Logistic Regression
- Random Forest Classifier

The models were evaluated using Accuracy, Precision, Recall, F1-Score and ROC-AUC.

---

## Objectives

- Analyse fraudulent and genuine transaction patterns.
- Understand class imbalance in financial transaction data.
- Perform exploratory data analysis (EDA).
- Apply SMOTE to handle class imbalance.
- Train Logistic Regression and Random Forest models.
- Evaluate and compare model performance.
- Identify important features influencing fraud predictions.
- Discuss scalability for large-scale transaction processing.

---

## Dataset

**Dataset:** Credit Card Fraud Detection

**Source:** [Kaggle – Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

The dataset contains European credit card transactions made in September 2013.

| Attribute | Details |
|---|---|
| Original transactions | 284,807 |
| Genuine transactions | 284,315 |
| Fraudulent transactions | 492 |
| Total features | 30 input features |
| Target column | Class |

The `Class` column represents:
- `0` – Genuine transaction
- `1` – Fraudulent transaction

Most features (`V1` to `V28`) are transformed using PCA. The dataset also contains `Time` and `Amount`.

---

## Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn

---

## Project Workflow

### 1. Data Inspection

- Loaded the credit card transaction dataset.
- Inspected dataset dimensions and data types.
- Checked missing values and duplicate records.
- Analysed the distribution of genuine and fraudulent transactions.

### 2. Exploratory Data Analysis

Performed visual analysis of:
- Class distribution.
- Transaction amount
