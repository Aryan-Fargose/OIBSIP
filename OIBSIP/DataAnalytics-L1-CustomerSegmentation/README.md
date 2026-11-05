# Customer Segmentation Analysis using K-Means Clustering

**OIBSIP – Data Analytics Internship | Level 1 | Task 2**

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Scikit Learn](https://img.shields.io/badge/Scikit--Learn-KMeans-orange?logo=scikitlearn)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 1. Project Overview

This project focuses on analysing e-commerce customer purchasing behaviour and dividing customers into meaningful segments using the **K-Means Clustering algorithm**.

The project uses RFM (Recency, Frequency and Monetary) analysis to identify customer behaviour patterns and develop targeted marketing strategies.

The primary objective is to help businesses understand their customers, improve customer retention, identify high-value customers and make data-driven marketing decisions.

## 2. Project Objectives

- Analyse customer purchasing behaviour.
- Perform data cleaning and preprocessing.
- Calculate Recency, Frequency and Monetary (RFM) metrics.
- Standardise behavioural features using StandardScaler.
- Determine the optimal number of clusters using the Elbow Method.
- Apply K-Means clustering.
- Visualise and interpret customer segments.
- Develop actionable marketing recommendations.

## 3. Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Matplotlib | Data visualisation |
| Seaborn | Statistical visualisation |
| Scikit-learn | Machine learning and clustering |
| Google Colab | Development environment |

## 4. Dataset Information

**Dataset:** Online Retail Dataset

**Source:** UCI Machine Learning Repository

[Download Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

The dataset contains transactions from a UK-based online retail business.

### Original Dataset Statistics

| Metric | Value |
|---|---:|
| Total records | 541,909 |
| Original columns | 8 |
| Unique customers | 4,372 |
| Countries | 38 |

### Important Features

| Feature | Description |
|---|---|
| InvoiceNo | Transaction identification number |
| StockCode | Product identification code |
| Description | Product description |
| Quantity | Number of products purchased |
| InvoiceDate | Transaction date and time |
| UnitPrice | Price per product |
| CustomerID | Customer identification number |
| Country | Customer's country |

## 5. Data Cleaning and Preprocessing

The original dataset was inspected and cleaned before performing customer segmentation.

The following operations were performed:

1. Removed records with missing CustomerID values.
2. Removed duplicate records.
3. Excluded cancelled invoices.
4. Removed transactions with negative or zero quantities.
5. Removed transactions with zero or negative unit prices.
6. Converted CustomerID into integer format.
7. Created a new TotalPrice column.

The TotalPrice feature was calculated using:

**TotalPrice = Quantity × UnitPrice**

### Cleaning Results

| Metric | Original | Cleaned |
|---|---:|---:|
| Rows | 541,909 | 392,692 |
| Columns | 8 | 9 |
| Missing values | Present | 0 |
| Duplicate records | 5,268 | 0 |

A total of **149,217 records** were removed during preprocessing.

## 6. RFM Analysis

RFM analysis was performed to understand customer purchasing behaviour.

Three behavioural features were calculated for each customer.

### 6.1 Recency (R)

Measures the number of days since a customer's most recent purchase.

Lower recency indicates more recent customer activity.

### 6.2 Frequency (F)

Measures the number of distinct invoices associated with each customer.

Higher frequency indicates more frequent purchasing behaviour.

### 6.3 Monetary (M)

Measures the total amount spent by a customer.

Calculated by summing the TotalPrice values for each customer.

### RFM Dataset Results

| Metric | Result |
|---|---:|
| Total customers | 4,338 |
| Behavioural features | 3 |
| Features | Recency, Frequency, Monetary |

## 7. Exploratory Data Analysis

The distributions of Recency, Frequency and Monetary values were examined to understand customer purchasing patterns.

### RFM Feature Distributions

![RFM Feature Distributions](visualizations/rfm_distributions.png)

**Observation:** The distributions help identify variations in customer activity, purchasing frequency and spending behaviour.

## 8. Feature Scaling

StandardScaler from Scikit-learn was applied to standardise the RFM features.

This was necessary because the features had different numerical ranges.

For example:
- Recency represents days.
- Frequency represents invoice counts.
- Monetary represents spending in pounds.

Standardisation ensures that features with larger numerical values do not disproportionately influence distance-based clustering.

## 9. Elbow Method

The Elbow Method was used to identify an appropriate number of clusters.

Within-Cluster Sum of Squares (WCSS) was calculated for K values ranging from 1 to 10
