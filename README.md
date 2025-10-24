# Unsupervised-Customer-Segmentation-using-K-Means-DBSCAN-and-Hierarchical-Clustering
End-to-end unsupervised learning project applying K-Means, DBSCAN, and Hierarchical Clustering to segment customers based on their buying patterns. The analysis identifies distinct customer groups to support data-driven marketing and business strategies.

## Project Objective

The goal of this analysis is to:
- Understand customer purchasing behavior using unsupervised learning.
- Identify **distinct customer segments** with algorithms like **K-Means**, **DBSCAN**, and **Hierarchical Clustering**.
- Visualize clusters and analyze feature patterns.
- Predict cluster membership for new data samples.

---

## Methodology

### 1. **Data Loading & Exploration**
- Dataset: `wholesale_clients.csv`
- Contains **440 samples** and **8 features**:
  - Spending categories: `Fresh`, `Milk`, `Grocery`, `Frozen`, `Detergents_Paper`, `Delicassen`
  - Categorical identifiers: `Channel`, `Region`
- Initial exploration included:
  - Checking for missing values
  - Feature distributions and correlations
  - Summary statistics

### 2. **Data Preprocessing**
- Normalized all numerical features using **StandardScaler** to prevent bias from large-scale variables.
- Optional outlier filtering and skew adjustments for better clustering performance.

### 3. **Clustering Algorithms**

#### � K-Means Clustering
- Applied **KMeans** from `sklearn.cluster`.
- Determined optimal cluster count using:
  - **Elbow Method** (distortion/inertia)
  - **Silhouette Score**
- Produced initial segmentation into **2–4 clusters**.
- Each cluster characterized by dominant product spending behavior (e.g., high Fresh, high Grocery, balanced spenders).

####  DBSCAN (Density-Based Spatial Clustering)
- Implemented **DBSCAN** to detect **arbitrary-shaped** clusters and outliers.
- Tuned parameters:
  - `eps` (neighborhood size)
  - `min_samples` (minimum core points)
- Identified **dense core regions** representing stable customer groups, ignoring noise/outliers.

####  Hierarchical Clustering (Agglomerative)
- Used **AgglomerativeClustering** with **linkage methods** such as *ward*, *average*, and *complete*.
- Constructed a **dendrogram** to visualize hierarchical relationships between customers.
- Determined the cut-off level to identify the ideal cluster grouping.

### 4. **Cluster Evaluation**
- Evaluated clusters with:
  - **Silhouette Score** (cohesion and separation)
  - **Inertia** (K-Means)
  - Visual comparisons between algorithms
- Compared performance across KMeans, DBSCAN, and Hierarchical clustering to find the most meaningful segmentation.

### 5. **Visualization**
- Used **Matplotlib** and **Seaborn** for plots:
  - Elbow and silhouette visualizations
  - Pair plots for key features (e.g., Milk vs Grocery, Fresh vs Frozen)
  - 2D scatter plots of clusters (color-coded)
  - Hierarchical dendrogram for visualizing linkage distance

### 6. **Prediction / Cluster Assignment**
- After fitting clustering models, assigned labels to each customer.
- Used the trained **KMeans model** to:
  - **Predict** the cluster label for new unseen customer data.

- **Pandas** – Data manipulation  
- **NumPy** – Numerical computations  
- **Matplotlib / Seaborn** – Data visualization  
- **Scikit-learn** – Machine learning (StandardScaler, KMeans, DBSCAN, AgglomerativeClustering)  
- **SciPy** – Hierarchical clustering and linkage functions  
