# 🛍️ Customer Segmentation Using K-Means Clustering

> Segment customers based on purchasing behavior using RFM analysis and K-Means clustering to enable targeted marketing and retention strategies.

---

## 📌 Overview

Businesses lose revenue by treating all customers the same. This project identifies distinct customer groups based on how **recently**, how **frequently**, and how much they **spend** — enabling personalised campaigns, loyalty programs, and win-back strategies per segment.

---

## 📊 Key Results

| Metric | Value |
|---|---|
| Records Processed | 541,909 transactions |
| Customers Segmented | 3 distinct groups |
| Validation Method | Elbow Method + Silhouette Score |
| Dataset | UCI Online Retail II |

---

## 🧩 Segments & Strategies

| Segment | Profile | Strategy |
|---|---|---|
| 🟢 Premium Loyal | High spend, high frequency, recent | Loyalty rewards, exclusive offers |
| 🟡 Engaged | Moderate spend and frequency | Bundle promotions, upselling |
| 🔴 At-Risk | Low recency, declining activity | Win-back campaigns, discounts |

---

## 🔬 Methodology

1. **Data Cleaning** — removed cancelled invoices, invalid stock codes, missing customer IDs, and negative prices
2. **RFM Feature Engineering** — computed Recency, Frequency, and Monetary Value per customer
3. **Outlier Treatment** — IQR-based removal on Monetary Value and Frequency
4. **Normalisation** — StandardScaler applied for equal feature contribution
5. **Clustering** — K-Means with optimal K via Elbow Method and Silhouette Score
6. **Segment Profiling** — behavioural profiles with targeted strategy recommendations

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat)

---

## 📁 Project Structure

```
Customer-Segmentation/
│
├── Python Notebook/
│   └── customer_segmentation_KMeans_Clustering.ipynb
└── README.md
```

---

