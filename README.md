# Customer Segmentation using K-Means Clustering

## Project Overview

This project focuses on customer segmentation using **RFM (Recency, Frequency, Monetary)** analysis and **K-Means Clustering** to identify meaningful customer groups based on purchasing behavior.

The goal of this project is to help businesses better understand customer purchasing patterns and support **personalized marketing, customer retention, and targeted promotional strategies**.

---

## Business Problem

Businesses often apply the same marketing strategy to all customers without understanding differences in purchasing behavior.

This project aims to:

- Identify distinct customer segments
- Understand purchasing behavior patterns
- Support personalized marketing strategies
- Improve customer retention and engagement

---

## Dataset Overview

The dataset contains customer transaction information used to analyze purchasing behavior and create customer-level features.

Key behavioral metrics include:

- **Recency** → How recently a customer purchased
- **Frequency** → How often a customer purchased
- **Monetary Value** → How much a customer spent

---

## Methodology

### 1. Data Cleaning & Preparation
- Missing value checks
- Duplicate validation
- Data preprocessing

### 2. RFM Feature Engineering
Built customer-level behavioral metrics:

- **Recency**
- **Frequency**
- **Monetary**

### 3. Outlier Handling
Outliers were identified and handled to improve clustering performance.

### 4. Feature Scaling
Applied **StandardScaler** because K-Means is distance-based and sensitive to feature scale.

### 5. K-Means Clustering
Implemented **K-Means clustering** to identify hidden customer groups.

### 6. Optimal Cluster Selection
Used:

- **Elbow Method**
- **Silhouette Score**

to determine the optimal number of clusters.

---

## Customer Segments Identified

### 1. Premium Loyal Customers
- High purchase frequency
- High spending
- Recent purchases

### 2. Engaged Customers
- Moderate spending
- Active purchasing behavior
- Good engagement level

### 3. At-Risk Customers
- Lower spending
- Infrequent purchases
- Longer inactivity period

---

## Business Recommendations

### Premium Loyal Customers
Focus on retention through loyalty rewards, exclusive offers, and personalized experiences.

### Engaged Customers
Increase purchase frequency using promotions, bundles, and personalized recommendations.

### At-Risk Customers
Implement win-back campaigns, discount offers, and engagement strategies to reduce customer inactivity.

---

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- Seaborn

---

## Project Outcome

Customer segmentation helped identify three meaningful customer groups with different purchasing behaviors. These insights can support businesses in improving customer retention, marketing effectiveness, and long-term customer value.
