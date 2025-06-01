# Customer Segmentation using RFM Analysis and K-Means Clustering

## Project Description

This project aims to segment customers based on their purchasing behavior using the RFM (Recency, Frequency, Monetary) framework combined with K-Means clustering. The segmentation helps businesses understand their customers better and tailor marketing strategies accordingly to maximize retention and profitability.

---

## Dataset Overview

- **Transaction Data**: Contains 15,143 transactions from 500 unique customers.
- **Columns include**:
  - `TransactionID`
  - `CustomerID`
  - `TransactionDate`
  - `ProductID`
  - `Quantity`
  - `UnitPrice`
  - `TotalPrice`

The data covers transactions from 2022 to 2023 and includes 20 unique products.

---

## Step-by-Step Project Workflow

### 1. Data Loading and Initial Exploration
- Loaded transaction dataset using pandas.
- Checked for missing values (none found).
- Explored data summary statistics to understand distributions of Quantity, UnitPrice, and TotalPrice.
- Verified unique counts of customers, transactions, and products.

### 2. Calculating RFM Metrics
- Defined reference date for Recency calculation (latest transaction date + 1 day).
- Calculated:
  - **Recency**: Days since last purchase per customer.
  - **Frequency**: Number of transactions per customer.
  - **Monetary**: Total spending per customer.
- Created RFM dataframe indexed by CustomerID.

### 3. Exploratory Data Analysis (EDA)
- Visualized distributions of Recency, Frequency, and Monetary using histograms and boxplots.
- Identified skewness and outliers in monetary values.
- Applied log transformations where necessary to normalize data for clustering.

### 4. Data Scaling
- Used `StandardScaler` to standardize RFM features for better clustering performance.

### 5. Finding Optimal Number of Clusters
- Used **Elbow Method** (plotting inertia vs. number of clusters) to identify the optimal number of clusters (~4).
- Used **Silhouette Score** analysis to evaluate clustering quality (best score at k=3).
- Decided on **3 clusters** based on silhouette score peak and visual inspection.

### 6. Applying K-Means Clustering
- Applied K-Means clustering with k=3.
- Assigned cluster labels to each customer in the RFM dataframe.

### 7. Cluster Profiling and Interpretation
- Calculated average Recency, Frequency, and Monetary values per cluster.
- Named clusters based on their characteristics:
  - **Segment 0:** At-Risk Customers (High Recency, Low Frequency, Low Monetary)
  - **Segment 1:** Loyal High Spenders (Moderate Recency, High Frequency, High Monetary)
  - **Segment 2:** Recent Potential Loyalists (Low Recency, Moderate Frequency, Moderate Monetary)
- Counted customers in each segment.

### 8. Visualization
- Created scatter plots and bar charts to visualize clusters and their features.
- Used PCA for 2D visualization of cluster separation.

### 9. Reporting and Recommendations
- Summarized insights about customer behavior by segment.
- Suggested targeted marketing strategies for each segment to improve engagement and profitability.

---

## Project Deliverables

- **Jupyter Notebook:** Full analysis pipeline from data loading to clustering and visualization.
- **CSV file:** Contains CustomerID and their assigned cluster labels for future use.
- **Presentation:** Detailed slides explaining methodology, findings, and marketing recommendations.

---

## Technologies Used

- Python libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
- Jupyter Notebook for interactive analysis
- Git and GitHub for version control and project hosting

---


