# 🛍 Customer Segmentation (Mall Customers Dataset)

## 📌 Project Overview
This project applies clustering techniques to segment mall customers into distinct groups based on their age, annual income, and spending score.  
Understanding customer segments helps businesses design better marketing strategies and improve customer experience.

---

## 📂 Dataset
- Name: Mall Customers Dataset  
- Source: [Kaggle - Mall Customer Segmentation Data](https://www.kaggle.com/datasets/shwetabh123/mall-customers)  
- Shape: 200 rows × 5 columns

*Features:*
- CustomerID: Unique identifier for each customer  
- Genre: Gender (Male/Female)  
- Age: Customer age in years  
- Annual Income (k$): Annual income in thousand dollars  
- Spending Score (1-100): Score assigned by the mall based on customer behavior  

---

## ⚙ Steps & Methodology

### 1. Data Cleaning
- Checked for missing and duplicated values  
- Handled outliers using boxplots for numerical features  

### 2. Exploratory Data Analysis (EDA)
- Distribution of spending score, income, and age  
- Relationships between Age, Annual Income, Spending Score, and Genre  
- Visualizations using histograms, scatterplots, and boxplots  

### 3. Preprocessing
- Dropped CustomerID  
- Applied OneHot Encoding for Genre  
- Applied StandardScaler for normalization  

### 4. Modeling
#### 🔹 K-Means Clustering
- Used the Elbow Method to determine optimal k  
- Chose *k = 5 clusters*  
- Visualized clusters based on Annual Income and Spending Score  

#### 🔹 DBSCAN
- Applied density-based clustering to detect non-linear groups  

#### 🔹 Hierarchical Clustering
- Built a dendrogram to explore possible cluster merges  

### 5. Cluster Profiling
- Analyzed each cluster by average Age, Annual Income, and Spending Score  

*Example insights:*  
- Cluster 2 → Younger customers with higher spending scores  
- Cluster 1 → High-income customers with low spending scores  

---

## 📊 Results
- *Optimal K (Elbow Method):* 5 clusters  

### Cluster Profiles  

| Cluster | Age | Annual Income (k$) | Spending Score (1-100) | Notes |
|---------|-----|---------------------|-------------------------|-------|
| 0 | ~56 | ~46 | ~39 | Older customers, moderate income, average spend |
| 1 | ~39 | ~85 | ~14 | High income but low spending |
| 2 | ~28 | ~61 | ~70 | Young, middle-income, high spending |
| 3 | ~38 | ~82 | ~54 | High income and high spending (valuable customers) |
| 4 | ~27 | ~39 | ~56 | Young, low income, moderate spending |

*Visualizations:*
- K-Means clusters on income vs spending score  
- Heatmap of average values per cluster  
- DBSCAN clusters  
- Dendrogram for hierarchical clustering  

---

## 🛠 Tools & Libraries
- *Python*  
- *Pandas, NumPy*  
- *Matplotlib, Seaborn*  
- *Scikit-learn (KMeans, DBSCAN, StandardScaler)*  
- *SciPy (Hierarchical Clustering)*  

---

## 🚀 Key Takeaways
- K-Means effectively segmented customers into 5 distinct groups.  
- DBSCAN highlighted noise and density-based patterns but was less stable.  
- Hierarchical clustering provided additional insights into customer grouping.  
- These insights can be used by businesses to design targeted marketing campaigns and personalized offers.  

---