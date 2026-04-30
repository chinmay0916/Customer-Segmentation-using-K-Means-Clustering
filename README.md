# Customer-Segmentation-using-K-Means-Clustering
This project performs K-Means clustering on mall customer data. It segments customers into five groups based on age, income, and spending score. The analysis includes EDA, feature scaling, optimal K determination, and visualization to provide targeted business insights and predict new customer segments.
# Mall Customer Segmentation Project

## Overview
This project focuses on applying K-Means clustering to segment mall customers based on their demographic and behavioral data. The goal is to identify distinct customer groups to enable targeted marketing strategies and improve customer engagement.

## Dataset

The dataset used is `mall_customers.csv`, which contains information about 200 mall customers. The key features include:
- `CustomerID`: Unique ID for each customer.
- `Gender`: Gender of the customer.
- `Age`: Age of the customer.
- `Annual_Income_kUSD`: Annual income of the customer in thousands of US dollars.
- `Spending_Score`: A score (1-100) assigned by the mall based on spending behavior and nature of purchase.

## Methodology

1.  **Data Loading & Initial Exploration**: Loaded the `mall_customers.csv` dataset and performed initial checks for shape, columns, data types, and missing values. Descriptive statistics were also generated.
2.  **Exploratory Data Analysis (EDA)**: Visualizations were created to understand the distribution of key features (`Age`, `Annual_Income_kUSD`, `Spending_Score`, `Gender`) and their relationships. This included histograms, scatter plots, box plots, and a correlation heatmap.
3.  **Feature Preprocessing**: Numerical features (`Annual_Income_kUSD`, `Spending_Score`, `Age`) were scaled using `StandardScaler` to ensure that no single feature dominates the clustering process. Gender was label-encoded for comprehensive clustering.
4.  **Determining Optimal Number of Clusters (K)**: The Elbow Method (using WCSS) and Silhouette Score analysis were employed to identify the most appropriate number of clusters for the K-Means algorithm. Both methods indicated an optimal `K=5`.
5.  **K-Means Clustering**: The K-Means algorithm was applied with `K=5` to segment the customers. Each customer was assigned to a cluster, and meaningful labels were given to each segment based on their characteristics.
6.  **Cluster Visualization & Analysis**: Various plots were generated to visualize the clusters, including scatter plots of Income vs. Spending Score, Age vs. Spending Score, and Age vs. Income, with cluster assignments highlighted. A PCA 2D visualization was also used to represent the clusters from all features. Cluster sizes and feature means were also compared.

## Results & Business Insights

Five distinct customer segments were identified:

1.  **Low Income – Low Spend (Budget)**: Customers with lower income and lower spending scores. 
    *Strategy*: Attract with discounts, bundle deals, and affordable product lines.
2.  **High Income – High Spend (Target)**: The most valuable segment, with high income and high spending scores. 
    *Strategy*: Offer premium loyalty programs, VIP memberships, early access to new products.
3.  **High Income – Low Spend (Careful)**: Customers with high income but lower spending scores. 
    *Strategy*: Win with trust – quality guarantees, reviews, exclusive value-for-money deals.
4.  **Average – Moderate Spend (Standard)**: Customers with average income and moderate spending scores. 
    *Strategy*: Nurture with regular promotions, referral bonuses, seasonal offers.
5.  **(Re-identified as High Income – Low Spend (Careful) in this run due to similar characteristics to Cluster 2)**: Customers with high income but lower spending scores. 
    *Strategy*: Same as Cluster 2, focus on building trust and offering value. 

The project also includes a capability to predict the segment for new customers, allowing for real-time application of these insights.

## Setup and Usage

To run this notebook:
1.  Ensure you have `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scikit-learn` installed.
2.  Upload `mall_customers.csv` to your Colab environment or update the path in the 'Loading Dataset' section.
3.  Execute the cells sequentially.
