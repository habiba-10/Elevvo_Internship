# 🎬 Movie Recommendation System

## 📌 Project Overview
This project implements a *User-Based Collaborative Filtering* recommendation system using the *MovieLens 100K dataset*.  
The system recommends movies to users based on the preferences of similar users.

*Workflow includes:*
- Data loading and cleaning  
- Exploratory Data Analysis (EDA)  
- Building a User-Item Matrix  
- Computing User Similarity with Cosine Similarity  
- Generating Recommendations for each user  
- Evaluating the system with *Precision@K*  

---

## 📂 Dataset
- *Ratings dataset:* Contains userId, movieId, rating, and timestamp  
- *Movies dataset:* Metadata including title, release date, and genres  
- *Source:* [MovieLens Dataset (Kaggle)](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset)  

---

## ⚙ Tools & Libraries
- *Python 3*  
- *Pandas, NumPy* → Data manipulation  
- *Matplotlib, Seaborn* → Visualization & EDA  
- *Scikit-learn* → Similarity computation (cosine similarity)  
- *Collections* → Efficient data handling  

---

## 🔑 Steps

### 1. Data Preparation
- Loaded ratings and movies metadata  
- Checked for null values, duplicates, and outliers  
- Converted IDs to integer format for merging  

### 2. Exploratory Data Analysis (EDA)
- Visualized rating distribution  
- Plotted ratings per user and per movie  
- *Insights:* Most users rate few movies, and most movies have relatively few ratings  

### 3. User-Item Matrix
- Constructed a matrix with users as rows and movies as columns  
- Missing values replaced with *zeros* for similarity computation  

### 4. User-Based Collaborative Filtering
- Calculated *cosine similarity* between users  
- For a target user:  
  - Found the *top-N most similar users*  
  - Recommended movies *highly rated by similar users* but unseen by the target user  

### 5. Train/Test Split
- Performed a *per-user holdout split* (train/test) for fair evaluation  
- Built user-item matrix from *train set only*  

### 6. Evaluation
- Used *Precision@K (K=10)* to measure recommendation quality  

*Result:*  
- Evaluated on *671 users*  
- Mean Precision@10 ≈ *0.0699 (~7%)*  

### 7. Sample Recommendations
*Example generated recommendations:*  

- *User 1:* Walk the Line, Men in Black II, Sleepless in Seattle, Snakes on a Plane  
- *User 2:* The Day After Tomorrow, The Million Dollar Hotel, Men in Black II  

---

## 📊 Results & Insights
- The system generates *reasonable recommendations* based on similar users  
- Precision@10 (~7%) is typical for *basic user-based collaborative filtering*  
- *Performance improvements possible via:*  
  - Item-Based Collaborative Filtering  
  - Matrix Factorization (SVD, ALS)  
  - Hybrid Approaches  

---

## 🚀 How to Run
1. Clone the repository or download the code  
2. Install dependencies:  
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
