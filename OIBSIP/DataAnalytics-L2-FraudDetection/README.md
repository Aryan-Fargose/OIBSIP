# Credit Card Fraud Detection

### OIBSIP Data Analytics Internship | Level 2 – Task 3

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-orange)
![Scikit Learn](https://img.shields.io/badge/Scikit--Learn-ML-yellow?logo=scikitlearn)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 1. Project Overview

This project focuses on detecting fraudulent credit card transactions using machine learning classification algorithms.

The main objective is to identify suspicious transactions from a highly imbalanced financial dataset and compare the performance of two machine learning models:

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

The dataset contains transactions made by European cardholders in September 2013.

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
- Examined the distribution of fraud and genuine transactions.

### Step 2: Exploratory Data Analysis

Performed visual analysis of:
- Transaction class distribution.
- Transaction amount distribution.
- Fraudulent versus genuine transaction amounts.
- Transaction time distribution.

### Step 3: Handling Class Imbalance

The dataset contains very few fraudulent transactions compared with genuine transactions.

SMOTE (Synthetic Minority Over-sampling Technique) was applied to the training dataset to generate synthetic minority-class samples.

A stratified train-test split was used to preserve the original class proportions.

**Important:** SMOTE was applied only to the training data. The test data retained its original distribution to prevent data leakage.

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

The following evaluation metrics were used:

| Metric | Description |
|---|---|
| Accuracy | Overall proportion of correct predictions |
| Precision | Proportion of predicted fraud cases that were actually fraudulent |
| Recall | Proportion of actual fraud cases successfully detected |
| F1-Score | Harmonic mean of Precision and Recall |
| ROC-AUC | Measures the model's ability to distinguish between classes |

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

# 6. Data Visualizations

The following visualizations were generated during the analysis.

### 6.1 Class Distribution

Shows the imbalance between genuine and fraudulent transactions.

![Class Distribution](visualizations/class_distribution.png)

### 6.2 Transaction Amount Distribution

Displays the distribution of transaction amounts.

![Transaction Amount Distribution](visualizations/transaction_amounts.png)

### 6.3 Fraud vs Genuine Transaction Amounts

Compares transaction amount distributions across both classes.

![Fraud vs Genuine](visualizations/fraud_vs_genuine.png)

### 6.4 Transaction Time Distribution

Displays transactions against elapsed time from the first transaction.

![Transaction Time](visualizations/transaction_time.png)

**Note:** The dataset's `Time` column represents elapsed seconds, not actual clock time.

### 6.5 SMOTE Class Balancing

Compares class distribution before and after applying SMOTE to the training dataset.

![SMOTE Comparison](visualizations/smote_comparison.png)

### 6.6 Logistic Regression Confusion Matrix

Shows the classification results of Logistic Regression.

![Logistic Regression Confusion Matrix](visualizations/confusion_matrix_lr.png)

### 6.7 Random Forest Confusion Matrix

Shows the classification results of Random Forest.

![Random Forest Confusion Matrix](visualizations/confusion_matrix_rf.png)

### 6.8 ROC Curve Comparison

Compares the classification performance of both models using ROC curves.

![ROC Curve](visualizations/roc_curve.png)

### 6.9 Model Performance Comparison

Compares Accuracy, Precision, Recall, F1-Score and ROC-AUC.

![Model Comparison](visualizations/model_comparison.png)

### 6.10 Feature Importance

Displays the top 15 features according to Random Forest feature importance.

![Feature Importance](visualizations/feature_importance.png)

---

## 7. Model Performance Results

The project evaluates both models using five classification metrics.

| Evaluation Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | Refer to CSV | Refer to CSV |
| Precision | Refer to CSV | Refer to CSV |
| Recall | Refer to CSV | Refer to CSV |
| F1-Score | Refer to CSV | Refer to CSV |
| ROC-AUC | Refer to CSV | Refer to CSV |

For exact numerical results and training times, refer to:

- `results/final_model_results.csv`
- `results/model_comparison.csv`

Feature importance values are available in `results/feature_importance.csv`.

## 8. Project Structure

```text
DataAnalytics-L2-FraudDetection/
│
├── OIBSIP_Task3_Fraud_Detection.ipynb
├── README.md
│
├── results/
│   ├── final_model_results.csv
│   ├── model_comparison.csv
│   └── feature_importance.csv
│
└── visualizations/
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

**Repository:** [OIBSIP – GitHub](https://github.com/Aryan-Fargose/OIBSIP)
