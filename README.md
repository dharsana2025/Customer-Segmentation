# Algorithmic Customer Segmentation: RFM Feature Engineering & K-Means Clustering

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/dharsana2025/Customer-Segmentation/blob/main/Python%20Notebook/customer_segmentation_KMeans_Clustering.ipynb)

## 📌 Project Overview
This project delivers an end-to-end customer segmentation framework utilizing the **Online Retail II dataset (525,461 initial rows)**. Instead of applying unsupervised learning directly to raw transactional logs, the pipeline first implements an **RFM (Recency, Frequency, Monetary) behavioral model** to extract structured domain-specific features per customer. These standardized dimensions are then processed via optimized **K-Means Clustering** to isolate distinct behavioral cohorts for automated, targeted marketing and retention strategies.

### 📊 The RFM Framework Core
* **Recency (R):** Days since the customer's last transaction. Tracks engagement decay.
* **Frequency (F):** Total number of distinct completed purchases. Measures loyalty and habituation.
* **Monetary (M):** Total capital spent across the customer's history. Identifies financial value contribution.

---

## 🛠️ Tech Stack & Mathematical Architecture
* **Data Engineering & Behavioral Modeling:** `pandas`, `numpy`
* **Machine Learning Pipelines:** `sklearn.cluster.KMeans`
* **Feature Scaling & Preprocessing:** `sklearn.preprocessing.StandardScaler`
* **Statistical Optimization:** Interquartile Range (IQR) Proximity Boxing (Outlier Mitigation)
* **Dimensional Diagnostics:** Within-Cluster Sum of Squares (WCSS / Elbow Method), Silhouette Scores
* **Visualization Suite:** `seaborn`, `matplotlib`

---

## ⚙️ Core Data Engineering & Modeling Pipeline

### 1. Production-Grade Data Sanitization
* **Anomaly Isolation:** Evaluated transactional integrity by detecting and dropping negative quantities, invoice cancellations, and invalid unit prices ($\le 0$).
* **Identity Resolution:** Excluded rows missing a valid `Customer ID` to maintain clean tracking lineages across unique consumer profiles.

### 2. High-Fidelity RFM Feature Engineering
Instead of relying on pre-aggregated data, a custom ETL pipeline was engineered to transition raw row-level transactional records into user-level behavioral dimensions:
* **Recency (R) Calculation:** Identified the global maximum transaction date within the entire dataset to establish an operational baseline. For each unique customer, the delta (in days) between their most recent transaction date and the baseline date was computed.
* **Frequency (F) Calculation:** Aggregated unique purchase events by isolating the count of distinct invoice numbers associated with each unique customer identifier, capturing actual buying cycles rather than line-item volumes.
* **Monetary (M) Calculation:** Engineered a composite price feature at the item line level ($\text{Quantity} \times \text{UnitPrice}$) and aggregated the cumulative financial sum for each customer profile.

### 3. Statistical Scaling & Outlier Mitigation
* **Statistical Clipping:** Because distance-based spatial algorithms like K-Means are highly sensitive to extreme financial scale variance, an **Interquartile Range (IQR)** filter was established to bound outliers, stabilizing cluster centroids and maximizing clear geometric separation.
* **Z-Score Feature Standardization:** Applied `StandardScaler` to bring variance-heavy RFM variables onto a uniform mathematical scale, preventing the high-magnitude Monetary column from dominating distance metrics during clustering.

### 4. Clustering Diagnostics & Optimization
* Executed iterative K-Means models across a broad hyperparameter space ($K$).
* Plotted the **WCSS Elbow Curve** to determine the point of diminishing mathematical returns for intra-cluster variance compression.
* Validated cluster density and cohesion boundaries using **Silhouette Score Analysis** to ensure distinct, non-overlapping customer cohorts.

---

## 🎯 Strategic Business Activations & Cohort Mapping
The integrated RFM + K-Means model translates raw transactional logs into high-impact, actionable marketing pathways:

* **High-Value Segments (Champions):** Top-tier Frequency and Monetary scores paired with low Recency gaps. 
  * *Strategy:* Enroll in VIP loyalty programs, grant early access to product rollouts, and utilize high-tier threshold upsells to maximize customer lifetime value (CLV).
* **Declining / At-Risk Segments:** High historical Frequency and Monetary values, but with widening Recency gaps.
  * *Strategy:* Trigger automated win-back workflows, targeted high-incentive promotional discounts, and feedback loops to proactively catch and stop permanent churn.
* **Core Stability Segments:** Mid-tier, predictable purchasing rhythms across all three RFM spectrums.
  * *Strategy:* Run personalized cross-category product recommendations to expand shopping basket breadth and drive incremental conversion velocity.
