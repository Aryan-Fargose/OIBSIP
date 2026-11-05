# Customer Segmentation Analysis using K-Means Clustering

**OIBSIP – Data Analytics Internship | Level 1 | Task 2**

---

## 1. Project Overview

This project focuses on analysing e-commerce customer purchasing behaviour and dividing customers into meaningful segments using **K-Means Clustering**.

The project uses RFM (Recency, Frequency and Monetary) analysis to identify customer behaviour patterns and develop targeted marketing strategies.

The objective is to help businesses understand their customers, improve retention and identify high-value customers.

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
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualisation |
| Seaborn | Statistical visualisation |
| Scikit-learn | Machine learning |
| Google Colab | Development environment |

## 4. Dataset Information

**Dataset:** Online Retail Dataset

**Source:** UCI Machine Learning Repository

https://archive.ics.uci.edu/dataset/352/online+retail

The dataset contains transactions from a UK-based online retail business.

Original dataset:
- Records: 541,909
- Columns: 8
- Unique customers: 4,372
- Countries: 38

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

TotalPrice = Quantity × UnitPrice

### Cleaning Results

| Metric | Original | Cleaned |
|---|---:|---:|
| Rows | 541,909 | 392,
