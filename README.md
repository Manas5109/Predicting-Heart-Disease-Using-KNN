Heart Disease Prediction Using KNN

Overview

This project builds a K-Nearest Neighbors (KNN) classification model to predict the likelihood of heart disease in patients based on clinical and physiological features. The dataset contains 500 patient records with 7 features including Age, Gender, Blood Pressure, Cholesterol, Heart Rate, Quantum Pattern Feature, and the target variable Heart Disease. Using the Elbow Method to find the optimal K value, the final model achieved an overall accuracy of 84% with a strong recall of 89% for heart disease detection — critical in medical applications to minimise false negatives.

---

Dataset

Source:   Heart Prediction Quantum Dataset (CSV)
Records:  500 entries
Features: Age, Gender, BloodPressure, Cholesterol, HeartRate, QuantumPatternFeature, HeartDisease
Missing Values: None
Duplicates: None
Target: HeartDisease (0 = No Disease, 1 = Heart Disease)

---

Project Workflow

Step 1 — Data Loading and Inspection
Loaded dataset using Pandas read_csv. Inspected structure using head(), tail(), info(), and describe(). Confirmed 500 records with zero null values and zero duplicate entries.

Step 2 — Exploratory Data Analysis
Computed detailed statistics using Om_stats library for every column including mean, median, mode, variance, standard deviation, skewness, kurtosis, IQR, and whisker values. Generated distribution plots using sns.displot for all features to understand data spread. Generated boxplots across all numerical columns to detect outliers. BloodPressure ranged between 90 and 179 with Q1=111, Q3=155, IQR=44.

Step 3 — Correlation Analysis
Generated a Seaborn correlation heatmap to identify feature relationships. Key findings: Cholesterol showed a strong positive correlation (0.55), Age had a moderate negative correlation (-0.38) with QuantumPatternFeature, and Cholesterol had a notable negative correlation (-0.42) with HeartDisease.

Step 4 — Data Preprocessing
Separated features (X) and target (y). Applied StandardScaler to normalise all features — essential for KNN since it is a distance-based algorithm. Split data into 80% training and 20% testing using train_test_split.

Step 5 — Finding Optimal K using Elbow Method
Iterated KNN classifier for K values from 1 to 20 using Euclidean distance. Computed error rate for each K and plotted the Elbow Curve. Identified K=16 as the optimal value with the lowest stable error rate of approximately 0.16.

Step 6 — Model Training and Evaluation
Trained final KNN model with n_neighbors=16 and metric='euclidean'. Evaluated on the test set using a Classification Report.

---

Results

                  Precision   Recall   F1-Score   Support
Class 0 (No Disease)   0.86     0.79      0.82       47
Class 1 (Heart Disease) 0.82    0.89      0.85       53
Overall Accuracy                          0.84      100
Macro Average          0.84     0.84      0.84      100
Weighted Average       0.84     0.84      0.84      100

Key Highlight: Recall of 89% for Class 1 means the model correctly identifies 89% of actual heart disease cases, minimising dangerous false negatives.

---

Technologies Used

Language:         Python 3.x
Data Manipulation: Pandas, NumPy
Visualisation:    Matplotlib, Seaborn
Machine Learning: Scikit-learn (KNeighborsClassifier, StandardScaler, train_test_split)
Statistics:       Om_stats
IDE:              Jupyter Notebook

---

Files in This Repository

Predicting Heart Disease Using KNN.ipynb  —  Main Jupyter Notebook
Heart Prediction Quantum Dataset.csv      —  Dataset
README.md                                 —  Project documentation

---

How to Run

1. Clone this repository
2. Install required libraries:
   pip install pandas numpy scikit-learn matplotlib seaborn
3. Open Jupyter Notebook and run all cells sequentially

---

Key Learnings

- KNN requires feature scaling — StandardScaler is essential for distance-based algorithms
- The Elbow Method is effective for selecting optimal K without overfitting
- High recall for the positive class is more important than precision in medical diagnosis
- A clean dataset with no missing values significantly reduces preprocessing effort

---

Author

Manas Patil
B.Sc. Information Technology — B.K. Birla College, Kalyan (Expected May 2026)
Email:    patilmanas5109@gmail.com
LinkedIn: linkedin.com/in/manaspatil07
GitHub:   github.com/Manas5109
