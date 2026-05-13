# ARTI-308-lab11

# Credit Card Customer Segmentation 

## Project Overview
This project applies unsupervised machine learning techniques to segment credit card customers based on their usage behavior. By grouping similar customers together, the company can better understand different customer profiles and tailor targeted marketing strategies to maximize engagement and profitability.

The project utilizes **K-Means Clustering** to identify distinct customer segments and **Principal Component Analysis (PCA)** to visualize these high-dimensional clusters in a 2D space.

## Dataset
The dataset (`CC_GENERAL.csv`) summarizes the usage behavior of credit card holders. 
* **Data points:** Various behavioral variables such as Balance, Purchases, Cash Advance, Payments, Credit Limit, and Tenure.
* **Target Label:** None (This is an Unsupervised Learning problem).

## Technologies Used
* **Python 3**
* **Pandas & NumPy:** Data manipulation and numerical computations
* **Scikit-Learn:** Machine learning (K-Means, PCA, StandardScaler, Silhouette Score)
* **Matplotlib & Seaborn:** Data visualization

## Project Workflow
1. **Data Cleaning:** * Dropped non-behavioral columns (e.g., `CUST_ID`).
   * Handled missing values in `CREDIT_LIMIT` and `MINIMUM_PAYMENTS` using mean imputation.
2. **Exploratory Data Analysis (EDA):** * Visualized distributions using histograms.
   * Examined feature relationships using correlation heatmaps and scatter plots.
3. **Data Preprocessing:** * Applied `StandardScaler` to normalize the data, ensuring features with large magnitudes (like balance) do not dominate the distance calculations.
4. **Determining Optimal Clusters (K):** * Utilized the **Elbow Method** (Inertia) and **Silhouette Scores** to evaluate different values of K. 
   * Selected **K = 4** as the optimal number of clusters.
5. **Model Training & Profiling:** * Trained the K-Means algorithm with 4 clusters.
   * Aggregated data by cluster to understand the average behavior of each segment.
6. **Visualization:** * Applied PCA to reduce the dataset to 2 principal components for clear 2D scatter plot visualization of the clusters.

## Customer Segments Identified
Based on the K-Means clustering, customers were grouped into 4 distinct segments:

* **Cluster 0 (Cash Advance Users):** Customers with high balances who frequently use cash advances but have very low purchase frequency.
* **Cluster 1 (High-Value / VIP Customers):** Customers with the highest purchase volumes, highest balances, and highest credit limits. They use their cards aggressively for purchases.
* **Cluster 2 (Transactors / Careful Spenders):** Customers who make frequent purchases but maintain low balances, indicating they likely pay off their statement in full every month.
* **Cluster 3 (Inactive Customers):** Customers with very low overall activity, low balances, and minimal purchases or cash advances.

## Marketing Strategies
These segments provide actionable business insights for tailored marketing:
* **High-Value Customers:** Retain them by offering premium reward programs, VIP perks, or cash-back incentives on large purchases.
* **Cash Advance Users:** Target them with promotional offers for personal loans or balance transfers at lower interest rates.
* **Transactors:** Encourage them to spend even more by offering point multipliers (e.g., 2x points on groceries) for specific categories.
* **Inactive Customers:** Re-engage them by sending targeted activation campaigns, such as a limited-time discount or a bonus reward for their next purchase.
