# 🌲 Forest Cover Type Classification (Covertype Dataset)

## 📌 Project Overview
This project predicts the type of forest cover based on cartographic variables using *Decision Tree, **Random Forest, and **XGBoost*.  
The task involves data cleaning, exploratory data analysis, feature selection, and model evaluation.

---

## 📂 Dataset
- *Name*: Covertype Dataset  
- *Source*: [UCI Machine Learning Repository - Covertype](https://archive.ics.uci.edu/dataset/31/covertype)  
- *Shape*: ~581,000 rows × 55 columns  

Features:  
- Elevation, Slope, Horizontal & Vertical distances to hydrology  
- Horizontal distance to roadways and fire points  
- Hillshade measurements (9am, Noon, 3pm)  
- Wilderness Area (binary one-hot features)  
- Soil Type (binary one-hot features)  
- *Target*: Cover_Type (7 forest cover categories)

---

## ⚙ Steps & Methodology

### 1. Data Cleaning
- Checked for missing values → None found  
- Checked for duplicated rows → None found  
- Outlier detection using IQR method  

### 2. Exploratory Data Analysis (EDA)
- Boxplots and histograms for numerical features  
- Countplots for Wilderness_Area and Soil_Type  
- Target variable (Cover_Type) distribution  
- Correlation heatmap among numerical features  
- Distribution of key numerical features by cover type  

### 3. Feature Selection
- Extracted *Top 30 important features* from each model (Decision Tree, Random Forest, XGBoost).  
- Visualized feature importance with bar plots.  

### 4. Modeling
#### 🔹 Decision Tree Classifier
- Tuned with max_depth=25  
- Evaluated on train/test splits  

#### 🔹 Random Forest Classifier
- Tuned with n_estimators=300, max_depth=25  
- Parallelized training (n_jobs=-1)  

#### 🔹 XGBoost Classifier
- Tuned with n_estimators=500, learning_rate=0.05, max_depth=12  
- Added regularization (reg_lambda=1.0) and subsampling  

### 5. Model Evaluation
- Metrics: Accuracy, F1-score, Classification Report, Confusion Matrix  

---

## 📊 Results

| Model           | Train Accuracy | Test Accuracy | Train F1 | Test F1 |
|-----------------|----------------|---------------|----------|---------|
| Decision Tree   | 0.9855         | 0.9309        | 0.9855   | 0.9308  |
| Random Forest   | 0.9873         | 0.9425        | 0.9872   | 0.9420  |
| XGBoost         | 0.9820         | *0.9501*    | 0.9819   | *0.9499* |

- *XGBoost* achieved the best performance with *95% accuracy* and highest F1-score.  
- *Random Forest* performed slightly below XGBoost but still strong.  
- *Decision Tree* was simpler but less accurate than ensemble models.  

Confusion Matrices:  
- Visualized per model for detailed class-level performance.  

---

## 🛠 Tools & Libraries
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn (DecisionTree, RandomForest, metrics)  
- XGBoost  

---

## 🚀 Key Takeaways
- *XGBoost* achieved the best performance with *95% accuracy* and highest F1-score.  
- *Random Forest* also performed strongly, slightly below XGBoost.  
- *Decision Tree* was simpler but less accurate compared to ensemble methods.  
- Certain classes (e.g., Cover Type 3 & 4) were more challenging due to imbalance.  

---