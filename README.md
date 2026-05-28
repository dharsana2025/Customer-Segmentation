#Customer Segmentation Using K-Means Clustering (RFM Based)
Segment customers based on purchasing behavior using RFM analysis and K-Means clustering to support targeted marketing and retention strategies.

##Business Problem
Businesses struggle to treat all customers the same way. This project identifies distinct customer groups based on how recently, how frequently, and how much they spend — enabling personalised marketing, loyalty programs, and win-back campaigns for each segment.

##Key Results

Processed 541,909 retail transaction records
Identified 3 distinct customer segments — Premium Loyal, Engaged, and At-Risk
Validated cluster quality using Elbow Method and Silhouette Score
Delivered segment-level marketing strategy recommendations


##Methodology

Data Cleaning — removed cancelled invoices, invalid stock codes, missing customer IDs, and negative prices
RFM Feature Engineering — computed Recency, Frequency, and Monetary Value per customer
Outlier Treatment — IQR-based outlier removal on Monetary Value and Frequency
Normalisation — StandardScaler applied to ensure equal feature contribution
Clustering — K-Means with optimal K selected via Elbow Method and Silhouette Score
Segment Profiling — behavioural profiles built per cluster with targeted strategy recommendations


##Segments & Strategies
SegmentProfileStrategyPremium LoyalHigh spend, high frequency, recentLoyalty rewards, exclusive offersEngagedModerate spend and frequencyBundle promotions, upsellingAt-RiskLow recency, declining activityWin-back campaigns, discounts

##Tech Stack
Python · Pandas · Scikit-learn · Matplotlib · Seaborn · NumPy
