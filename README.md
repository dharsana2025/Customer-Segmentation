# Algorithmic Customer Segmentation: End-to-End K-Means Clustering

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/dharsana2025/Customer-Segmentation/blob/main/Python%20Notebook/customer_segmentation_KMeans_Clustering.ipynb)

## 📌 Project Overview
This project builds a robust, unsupervised machine learning pipeline to segment an enterprise retail customer base using the **Online Retail II** dataset (**525,461 initial transactions**). By engineering behavioral features and executing strict statistical outlier suppression, this architecture clusters customers based on transaction behavior to drive automated, targeted downstream marketing and retention workflows.

### Pipeline Highlights
* **Data Scale:** 525,461 structural transaction records processed.
* **Mathematical Validation:** Joint **Elbow Method (WCSS)** and **Silhouette Coefficient Analysis** used to establish optimal mathematical cluster barriers.
* **Operational Goal:** Isolate high-value champions, steady regular buyers, and high-risk churning populations for targeted activation.

---

## 🛠️ Tech Stack & Mathematical Architecture
* **Data Engineering & Cleaning:** `pandas`, `numpy`
* **Machine Learning Pipelines:** `sklearn.cluster.KMeans`
* **Statistical Optimization:** Interquartile Range (IQR) Proximity Boxing
* **Dimensional Diagnostics:** Within-Cluster Sum of Squares (WCSS), Silhouette Scores
* **Visualization Suite:** `seaborn`, `matplotlib`

---

## ⚙️ Core Data Engineering Pipeline

### 1. Production-Grade Data Sanitization
* **Anomaly Isolation:** Detected and removed structural data noise including negative quantities, transaction cancellations, and invalid unit prices $\le 0$.
* **Missing Value Resolution:** Dropped missing `Customer ID` fields to guarantee tracking integrity across historical paths.

### 2. Statistical Outlier Suppression
* Because distance-based clustering algorithms (K-Means) are hyper-sensitive to extreme financial anomalies, an **Interquartile Range (IQR)** filter was established.
* Bound limits were calculated to truncate extreme outliers, stabilizing cluster centroids and maximizing clear geometric separation.

### 3. Model Optimization & Diagnostics
* Executed iterative K-Means algorithms across varying parameter spaces ($K$).
* Evaluated the mathematical inflection point via the **WCSS Elbow Curve**.
* Validated cluster density and cohesion via **Silhouette Analysis** to prevent segment overlap.

---

## 🎯 Strategic Business Activations
The final model uncovers clear customer sub-populations that map to distinct commercial actions:

* **High-Value Segments (Champions):** Characterized by high purchase volume and frequent activity. 
  * *Strategy:* Enroll in VIP retention programs, early product releases, and high-tier loyalty pathways.
* **Declining / At-Risk Segments:** Characterized by dropping order frequency and widening recency gaps.
  * *Strategy:* Trigger automated re-engagement workflows, win-back discounts, and feedback surveys to mitigate permanent churn.
* **Core Stability Segments:** Consistent, mid-tier transaction frequencies.
  * *Strategy:* Cross-sell related product categories and use personalized upsell thresholds to increase Average Order Value (AOV).
