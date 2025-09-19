# Loan Approval Prediction  

## 📌 Project Overview  
This project focuses on predicting loan approval status based on applicant information such as income, credit history, dependents, and loan amount.  
The dataset is imbalanced, so *SMOTE* was used to handle class imbalance.  
Multiple models were trained and compared, including Logistic Regression, Decision Tree, Random Forest, and XGBoost.  

Dataset: [Loan Prediction Dataset (Kaggle)](https://www.kaggle.com/datasets/ninzaami/loan-predication)  

---

## ⚙ Workflow  

1. *Data Cleaning*  
   - Handled missing values using median/mode imputation.  
   - Encoded categorical variables using Label Encoding.  
   - Detected and treated outliers with log transformation.  

2. *Exploratory Data Analysis (EDA)*  
   - Correlation heatmap for numerical features.  
   - Count plots and pie charts for categorical features.  
   - Scatterplots & histograms for income, loan amount, and credit history.  

3. *Feature Engineering*  
   - Created new features such as:  
     - Total_Income  
     - Loan_Income_Ratio  
     - Income_per_Person  

4. *Feature Selection*  
   - Applied *RFE (Recursive Feature Elimination)* with Logistic Regression.  

5. *Handling Imbalance*  
   - Used *SMOTE (Synthetic Minority Oversampling Technique)*.  

6. *Scaling*  
   - Standardized numerical features using StandardScaler.  

7. *Model Training & Evaluation*  
   - Logistic Regression  
   - Decision Tree  
   - Random Forest  
   - XGBoost  

---

## 📊 Results  

| Model                | Accuracy | F1 Score |
|-----------------------|----------|----------|
| Logistic Regression   | *0.81* | *0.87* |
| Random Forest         | 0.79     | 0.85     |
| XGBoost               | *0.83* | *0.87* |
| Decision Tree         | 0.72     | 0.78     |

✅ *Best Model:* XGBoost achieved the highest accuracy (0.83) and competitive F1-score (0.87), making it the most reliable choice for loan approval prediction.  

---

## 📂 Files  

- train.csv → Training dataset  
- test.csv → Test dataset  
- submission.csv → Final predictions using *XGBoost*  

---

## 🚀 How to Run  

```bash
# 1. Install required libraries
pip install numpy pandas scikit-learn imbalanced-learn xgboost seaborn matplotlib

# 2. Run the notebook/script step by step

# 3. Final predictions will be saved in:
submission.csv