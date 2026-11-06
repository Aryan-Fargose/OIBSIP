# Credit Card Fraud Detection

### OIBSIP Data Analytics Internship | Level 2 – Task 3

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-orange)
![Scikit Learn](https://img.shields.io/badge/Scikit--Learn-ML-yellow?logo=scikitlearn)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 1. Project Overview

This project focuses on detecting fraudulent credit card transactions using Machine Learning classification algorithms.

The objective is to identify suspicious transactions from a highly imbalanced financial dataset and compare the performance of two machine learning models:

- Logistic Regression
- Random Forest Classifier

The models are evaluated using Accuracy, Precision, Recall, F1-Score and ROC-AUC.

## 2. Project Objectives

- Analyse fraudulent and genuine credit card transactions.
- Perform Exploratory Data Analysis (EDA).
- Understand the challenges of imbalanced datasets.
- Apply SMOTE to balance the training dataset.
- Build Logistic Regression and Random Forest models.
- Evaluate and compare model performance.
- Identify important features influencing fraud predictions.
- Discuss scalability for large-scale transaction processing.

## 3. Dataset Information

**Dataset:** Credit Card Fraud Detection

**Source:** [Kaggle – Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

| Attribute | Details |
|---|---|
| Total transactions | 284,807 |
| Genuine transactions | 284,315 |
| Fraudulent transactions | 492 |
| Input features | 30 |
| Target column | Class |

The dataset contains credit card transactions made by European cardholders in September 2013.

- `Class = 0`: Genuine transaction
- `Class = 1`: Fraudulent transaction

Most features (`V1` to `V28`) are anonymized PCA-transformed features. The dataset also includes `Time` and `Amount`.

## 4. Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn

## 5. Project Workflow

### Step 1: Data Inspection

- Loaded the credit card transaction dataset.
- Inspected rows, columns and data types.
- Checked missing values and duplicate records.
- Examined the distribution of fraudulent and genuine transactions.

### Step 2: Exploratory Data Analysis

Performed visual analysis of:

- Transaction class distribution.
- Transaction amount distribution.
- Fraudulent versus genuine transaction amounts.
- Transaction time distribution.

### Step 3: Handling Class Imbalance

The dataset contains significantly fewer fraudulent transactions than genuine transactions.

SMOTE (Synthetic Minority Over-sampling Technique) was applied to the training dataset to generate synthetic minority-class samples.

A stratified train-test split was used to preserve the original class proportions.

**Important:** SMOTE was applied only to the training data. The test dataset retained its original distribution to prevent data leakage.

### Step 4: Model Development

**Logistic Regression**

- Used as a baseline classification algorithm.
- Trained on the SMOTE-balanced training dataset.

**Random Forest Classifier**

- Used an ensemble of decision trees.
- Configured with 50 estimators.
- Maximum tree depth set to 15.
- Class weighting enabled.

### Step 5: Model Evaluation

The following metrics were used:

| Metric | Description |
|---|---|
| Accuracy | Overall proportion of correct predictions |
| Precision | Proportion of predicted fraud cases that were actually fraudulent |
| Recall | Proportion of actual fraud cases successfully detected |
| F1-Score | Harmonic mean of Precision and Recall |
| ROC-AUC | Ability to distinguish between fraud and genuine transactions |

Accuracy alone can be misleading when working with highly imbalanced datasets. Precision and Recall are particularly important in fraud detection.

### Step 6: Feature Importance

Random Forest feature importance was used to identify which input features contributed most to the model's predictions.

### Step 7: Scalability Analysis

For a system processing one million transactions per hour, possible technologies include:

- Apache Kafka for transaction streaming.
- Apache Spark for distributed processing.
- REST APIs for real-time predictions.
- Cloud infrastructure with auto-scaling.
- Continuous monitoring and model retraining.

This is a proposed production architecture, not a real-time deployment implemented in this project.

---

# Visualizations

### 1. RFM Distributions

Shows the distribution of Recency, Frequency and Monetary values.

![RFM Distributions](https://raw.githubusercontent.com/Aryan-Fargose/OIBSIP/main/OIBSIP/DataAnalytics-L1-CustomerSegmentation/visualizations/rfm_distributions.png)

### 2. Elbow Method

Helps determine the optimal number of clusters for K-Means.

![Elbow Method](https://raw.githubusercontent.com/Aryan-Fargose/OIBSIP/main/OIBSIP/DataAnalytics-L1-CustomerSegmentation/visualizations/elbow_method.png)

### 3. Customer Cluster Distribution

Shows the number of customers assigned to each cluster.

![Cluster Distribution](https://raw.githubusercontent.com/Aryan-Fargose/OIBSIP/main/OIBSIP/DataAnalytics-L1-CustomerSegmentation/visualizations/cluster_distribution.png)

### 4. Recency vs Frequency

Visualizes customer segmentation based on Recency and Frequency.

![Recency vs Frequency](https://raw.githubusercontent.com/Aryan-Fargose/OIBSIP/main/OIBSIP/DataAnalytics-L1-CustomerSegmentation/visualizations/recency_frequency.png)

### 5. Frequency vs Monetary

Shows the relationship between customer purchase frequency and monetary value.

![Frequency vs Monetary](https://raw.githubusercontent.com/Aryan-Fargose/OIBSIP/main/OIBSIP/DataAnalytics-L1-CustomerSegmentation/visualizations/frequency_monetary.png)

## 7. Model Performance Results

The project evaluates both models using five classification metrics.

| Evaluation Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | Refer to results CSV | Refer to results CSV |
| Precision | Refer to results CSV | Refer to results CSV |
| Recall | Refer to results CSV | Refer to results CSV |
| F1-Score | Refer to results CSV | Refer to results CSV |
| ROC-AUC | Refer to results CSV | Refer to results CSV |

For exact numerical results and training times, refer to:

- `final_model_results.csv`
- `model_comparison.csv`

Feature importance values are available in `feature_importance.csv`.

## 8. Project Structure

```text
DataAnalytics-L2-FraudDetection/
│
├── OIBSIP_Task3_Fraud_Detection.ipynb
├── README.md
│
├── final_model_results.csv
├── model_comparison.csv
├── feature_importance.csv
│
├── class_distribution.png
├── transaction_amounts.png
├── fraud_vs_genuine.png
├── transaction_time.png
├── smote_comparison.png
├── confusion_matrix_lr.png
├── confusion_matrix_rf.png
├── roc_curve.png
├── model_comparison.png
└── feature_importance.png
```

## 9. Conclusion

This project demonstrates how machine learning algorithms can be applied to credit card fraud detection.

Logistic Regression and Random Forest were trained and evaluated using a highly imbalanced financial transaction dataset.

SMOTE was used to address class imbalance in the training data, while multiple evaluation metrics were used to assess model performance.

The project also demonstrates the importance of feature importance analysis and discusses how fraud detection systems can be scaled for high-volume transaction processing.

## 10. Internship Information

**Organization:** Oasis Infobyte

**Program:** Data Analytics Internship

**Track:** Data Analytics

**Level:** Level 2

**Task:** Task 3 – Fraud Detection

**Author:** [Aryan Fargose](https://github.com/Aryan-Fargose)

**GitHub Repository:** [OIBSIP](https://github.com/Aryan-Fargose/OIBSIP)
