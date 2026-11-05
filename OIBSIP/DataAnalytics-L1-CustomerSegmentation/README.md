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

Within-Cluster Sum of Squares (WCSS) was calculated for K values ranging from 1 to 10.

### Elbow Method Visualisation

![Elbow Method](visualizations/elbow_method.png)

Based on the observed elbow curve, **K = 3** was selected because the reduction in WCSS starts slowing down after this point.

## 10. K-Means Clustering

The K-Means algorithm was implemented using Scikit-learn.

### Model Configuration

| Parameter | Value |
|---|---|
| Algorithm | K-Means |
| Number of clusters | 3 |
| Initialisation | k-means++ |
| Random state | 42 |
| Number of initialisations | 10 |

The model successfully divided 4,338 customers into three distinct segments.

## 11. Customer Segmentation Results

The following results were obtained from the trained K-Means model.

| Cluster | Customers | Avg. Recency | Avg. Frequency | Avg. Monetary (£) |
|---|---:|---:|---:|---:|
| 0 | 1,082 | 247.11 | 1.58 | 629.66 |
| 1 | 3,230 | 41.45 | 4.67 | 1,849.67 |
| 2 | 26 | 6.04 | 66.42 | 85,826.08 |

### 11.1 Cluster 0 – At-Risk / Inactive Customers

- Customer count: 1,082
- Average Recency: 247.11 days
- Average Frequency: 1.58
- Average Monetary: £629.66

**Business Insight:**

These customers have relatively long periods since their last purchase and low purchasing frequency.

**Marketing Recommendations:**

- Introduce customer re-engagement campaigns.
- Provide personalised discounts.
- Send reminder emails.
- Encourage repeat purchases.

### 11.2 Cluster 1 – Regular Customers

- Customer count: 3,230
- Average Recency: 41.45 days
- Average Frequency: 4.67
- Average Monetary: £1,849.67

**Business Insight:**

This is the largest segment, consisting of customers who purchase relatively regularly and demonstrate comparatively recent activity.

**Marketing Recommendations:**

- Introduce loyalty programmes.
- Provide personalised product recommendations.
- Encourage cross-selling.
- Offer repeat-purchase incentives.

### 11.3 Cluster 2 – High-Value VIP Customers

- Customer count: 26
- Average Recency: 6.04 days
- Average Frequency: 66.42
- Average Monetary: £85,826.08

**Business Insight:**

This small segment demonstrates exceptionally high purchasing frequency and monetary value.

**Marketing Recommendations:**

- Provide exclusive rewards.
- Offer premium customer support.
- Introduce VIP membership benefits.
- Provide early access to new products.

## 12. Data Visualisations

### 12.1 Customer Cluster Distribution

This chart represents the number of customers assigned to each of the three clusters.

![Customer Cluster Distribution](visualizations/cluster_distribution.png)

**Observation:** Cluster 1 represents the largest customer segment, while Cluster 2 contains a small group of exceptionally high-value customers.

### 12.2 Recency vs Frequency

This scatter plot illustrates the relationship between customer purchase recency and purchase frequency across the identified customer segments.

![Recency vs Frequency](visualizations/recency_frequency.png)

**Observation:** The visualisation helps distinguish customers based on how recently and how frequently they purchase.

### 12.3 Frequency vs Monetary

This scatter plot compares purchasing frequency with total customer spending. A logarithmic scale is used for monetary value to make the differences easier to examine.

![Frequency vs Monetary](visualizations/frequency_monetary.png)

**Observation:** Cluster 2 demonstrates exceptionally high purchase frequency and monetary value compared with the other segments.

## 13. Key Business Insights

1. Most customers belong to Cluster 1, representing the regular customer segment.
2. Cluster 0 provides an opportunity for customer reactivation and retention campaigns.
3. Cluster 2 contains only 26 customers but demonstrates exceptionally high average spending.
4. RFM analysis helps businesses understand customer value and purchasing behaviour.
5. Customer segmentation enables targeted marketing instead of treating every customer identically.

## 14. Project Structure

```text
DataAnalytics-L1-CustomerSegmentation/
│
├── README.md
│
├── OIBSIP_Task2_Customer_Segmentation.ipynb
│
├── Customer_Segmentation_Results.csv
│
├── Customer_Cluster_Profile.csv
│
└── visualizations/
    ├── rfm_distributions.png
    ├── elbow_method.png
    ├── cluster_distribution.png
    ├── recency_frequency.png
    └── frequency_monetary.png
```

## 15. Project Outputs

The project includes:

- Complete Jupyter Notebook implementation.
- Cleaned customer-level RFM analysis.
- K-Means customer cluster assignments.
- Customer cluster profile.
- Five data visualisations.
- Business insights and marketing recommendations.

## 16. Conclusion

This project demonstrates the application of unsupervised machine learning for customer segmentation.

By combining RFM analysis, feature standardisation and K-Means clustering, 4,338 customers were successfully divided into three behavioural segments.

The resulting segments provide useful insights into customer purchasing behaviour and help businesses develop targeted marketing strategies, improve customer retention and identify high-value customers.

The project highlights how data analytics and machine learning can support practical business decision-making.

## 17. Author and Project Information

**Internship:** OIBSIP – Data Analytics

**Level:** Level 1

**Task:** Task 2 – Customer Segmentation Analysis

**Algorithm:** K-Means Clustering

**Dataset:** UCI Online Retail Dataset

**Repository:** [GitHub – Aryan-Fargose](https://github.com/Aryan-Fargose)

---
