# 🎓 Student Performance Prediction & Classification

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-Frontend-38B2AC)

A comprehensive Machine Learning pipeline designed to predict a student's final categorical grade (A, B, C, D, E, F) based on academic baseline scores and behavioral metrics. 

🔗 **[View the Jupyter Notebook Code Here](https://github.com/kaushik1506/ai-tech-gen-student-performance/blob/main/student_performance.ipynb)**

---

## 📖 Project Overview
This project transitions from predicting continuous numerical scores to a classification problem. By analyzing features such as `age`, `study_hours`, `attendance_percentage`, and subject-specific scores (`math`, `science`, `english`), the objective is to build a robust model capable of predicting the ultimate letter grade.

This repository contains the complete pipeline: from Exploratory Data Analysis (EDA) and data preprocessing to model hyperparameter tuning, evaluation, and an interactive HTML/JS simulation app.

## ⚙️ Tech Stack & Tools
* **Data Processing:** Python, Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (RandomForestClassifier, GridSearchCV)
* **Frontend App:** HTML5, Tailwind CSS, JavaScript

---

## 🔬 Methodology & Pipeline

### 1. Data Cleaning & Feature Engineering
* Removed noisy identifiers (e.g., `student_id`).
* **Target Isolation:** Dropped the `overall_score` column to prevent "data leakage," ensuring the model learns to map raw subject and behavioral metrics directly to the `final_grade`.
* Handled missing numerical values using the **median** and categorical values using the **mode**.
* Applied **One-Hot Encoding** (`pd.get_dummies`) to transform text-based categories into machine-readable binary columns.

### 2. Exploratory Data Analysis (EDA)
Several visualizations were generated to uncover patterns:
* **Grade Distribution (`grade_distribution.png`):** Ensured we understood the class imbalance to utilize stratified splitting.
* **Correlation Heatmap (`correlation_heatmap.png`):** Identified colinear features and primary drivers of student success (e.g., strong correlations between study hours and academic outcomes).
* **Pairplots (`pairplot_grades.png`):** Showcased distinct clustering of grades across multi-dimensional features, justifying the use of a non-linear, tree-based algorithm.

### 3. Model Training & Tuning
* **Data Split:** 80% Training / 20% Testing using a *Stratified Split* to ensure rare grades (like 'F') appeared proportionately in both sets.
* **Algorithm:** `RandomForestClassifier` was chosen for its resistance to overfitting and handling of complex feature relationships.
* **Optimization:** Deployed `GridSearchCV` to automatically test hundreds of hyperparameter combinations.
  * **Best Parameters Found:** `max_depth: None`, `n_estimators: 50`

### 4. Evaluation & Results
* **Accuracy:** The tuned model achieved a testing accuracy of **75.77%** on unseen data.
* **Confusion Matrix (`confusion_matrix.png`):** Because simple accuracy doesn't tell the full story in multi-class problems, the confusion matrix verified that misclassifications primarily only occur between borderline neighboring grades (e.g., confusing a high 'C' for a 'B').

---

## 💻 Interactive Prediction Web App

To make the machine learning model's concepts actionable and user-friendly, I developed a static frontend application (`student_performance_predictor.html`). It simulates the Random Forest's inference process, taking user input to generate a predicted grade and a mock confidence score.

### 🚀 How to Run the HTML App Locally
You do not need a backend server or Python installed to run the frontend simulation interface. 

1. **Clone or Download the Repository:**
   
```bash
   git clone [https://github.com/kaushik1506/ai-tech-gen-student-performance.git](https://github.com/kaushik1506/ai-tech-gen-student-performance.git)
   
