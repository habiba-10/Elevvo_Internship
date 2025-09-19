# 📚 Student Exam Score Prediction

## 📌 Project Overview
This project predicts student *exam scores* based on multiple academic, personal, and environmental factors using *regression models*.  
The goal is to identify key features affecting performance and evaluate different regression approaches to find the most effective model.

*Workflow includes:*
- Data loading & cleaning  
- Handling nulls, duplicates, and outliers  
- Exploratory Data Analysis (EDA)  
- Feature encoding & scaling  
- Training multiple regression models (Linear, Ridge, Lasso, ElasticNet, Polynomial)  
- Model evaluation using MAE, RMSE, and R²  

---

## 📂 Dataset
- *Name:* Student Performance Factors  
- *Source:* [Kaggle / Student Performance Dataset](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors)  
- *Shape:* ~ 3,000 rows × 20+ features  
- *Target Variable:* Exam_Score  

### Example Features:
- *Hours_Studied* (numeric)  
- *Attendance* (numeric)  
- *Previous_Scores* (numeric)  
- *Sleep_Hours* (numeric)  
- *Parental_Involvement, Teacher_Quality, Family_Income* (categorical, ordinal)  
- *Internet_Access, Extracurricular_Activities, Learning_Disabilities* (categorical, nominal)  

---

## ⚙ Tools & Libraries
- *Python 3*  
- *Pandas, NumPy* → Data handling  
- *Matplotlib, Seaborn* → Visualization  
- *Scikit-learn* → Preprocessing, modeling, evaluation  

---

## 🔑 Steps

### 1. Data Cleaning
- Checked dataset shape, dtypes, and summary stats  
- Filled missing values (Teacher_Quality, Parental_Education_Level, Distance_from_Home) with *mode*  
- Removed duplicates  
- Detected and handled outliers:  
  - *Removed:* Hours_Studied, Tutoring_Sessions  
  - *Clipped:* Exam_Score  

### 2. Exploratory Data Analysis (EDA)
- Relationship between *Exam_Score* and:  
  - Hours_Studied, Tutoring_Sessions, Attendance, Sleep_Hours, Previous_Scores  
  - School_Type, Parental_Education_Level, Parental_Involvement, Teacher_Quality  
- Distribution plots and heatmap for correlations  
- *Insights:* Hours studied, attendance, and previous scores are strong predictors  

### 3. Data Preprocessing
- *Label Encoding:* Extracurricular_Activities, Internet_Access, Learning_Disabilities  
- *One-Hot Encoding:* Gender, School_Type  
- *Ordinal Encoding:* Ordered features like Parental_Involvement, Access_to_Resources, Motivation_Level, etc.  
- *Scaling:* StandardScaler applied to numeric columns (Hours_Studied, Attendance, Sleep_Hours, Previous_Scores, Tutoring_Sessions)  

### 4. Train-Test Split
- Train/Test split = *80/20*  

### 5. Models Trained
- *Linear Regression*  
- *Ridge Regression* (L2 regularization)  
- *Lasso Regression* (L1 regularization)  
- *ElasticNet Regression* (L1 + L2 regularization)  
- *Polynomial Regression* (degree=2)  

### 6. Evaluation Metrics
- *MAE (Mean Absolute Error)*  
- *MSE (Mean Squared Error)*  
- *RMSE (Root Mean Squared Error)*  
- *R² (Coefficient of Determination)*  

---

## 📊 Results

| Model               | MAE   | MSE   | RMSE  | R²    |
|----------------------|-------|-------|-------|-------|
| Linear Regression    | 0.354 | 0.835 | 0.914 | 0.925 |
| Ridge Regression     | 0.354 | 0.835 | 0.914 | 0.925 |
| Lasso Regression     | 0.674 | 1.236 | 1.112 | 0.889 |
| ElasticNet Regression| 0.586 | 1.082 | 1.040 | 0.903 |
| Polynomial Regression| 0.391 | 0.867 | 0.931 | 0.922 |

*Insights:*
- *Linear and Ridge Regression performed best* with R² ≈ *0.925*  
- *Polynomial Regression* was slightly less accurate (R² ≈ 0.922)  
- *Lasso & ElasticNet* underperformed due to feature shrinkage  

---

## 📈 Visualizations
- Scatter plots of *Actual vs Predicted* scores for Linear & Polynomial Regression  
- Correlation Heatmap of features with Exam_Score  
- Comparison bar plots of *R²* and *RMSE* across models  

---

## 🚀 How to Run
1. Clone/download the repo  
2. Install dependencies:  
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn