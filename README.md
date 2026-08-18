# 📚 Credit Wise — Loan Approval Modeling Pipeline

**An end‑to‑end loan approval classification pipeline implemented in a single, production‑oriented Python script (`credit_wise.py`).**  
This project demonstrates data ingestion, missing‑value handling, exploratory data analysis (EDA), encoding, scaling, baseline model training, evaluation, and a concise feature‑engineering loop — all organized for clarity and recruiter review.

---

## 🚀 Workflow Overview

**Ingestion**  
Load the dataset from `loan_approval_data.csv` into a `pandas` DataFrame.

**Missing‑value handling**  
Impute numeric features with the mean and categorical features with the most frequent value using `SimpleImputer`.

**Exploratory Data Analysis (EDA)**  
Visualize class balance, distributions, boxplots, and a correlation heatmap using `seaborn` and `matplotlib` to inspect relationships and outliers.

**Encoding**  
Apply `LabelEncoder` for ordinal/binary labels and `OneHotEncoder(drop='first')` for nominal categorical features.

**Train/Test Split & Scaling**  
Split data with `train_test_split` and scale features with `StandardScaler` (fit on training data only).

**Modeling**  
Train and evaluate baseline classifiers: **Logistic Regression**, **K‑Nearest Neighbors (KNN)**, and **Gaussian Naive Bayes**.

**Evaluation**  
Report precision, recall, F1 score, accuracy, and confusion matrix for each model to compare performance.

**Feature Engineering**  
Add derived features (e.g., squared terms like `DTI_Ratio_sq`, `Credit_Score_sq`), retrain, and re‑evaluate to measure impact.

---

## 🧭 Architecture / Workflow (visual)

```mermaid
flowchart TD
  A[📂 loan_approval_data.csv] --> B[🔹 Load Data\n(pd.read_csv)]
  B --> C[🧹 Clean & Impute\n(SimpleImputer)]
  C --> D[🔎 EDA & Visualization\n(seaborn, matplotlib)]
  D --> E[🔤 Encoding\n(LabelEncoder, OneHotEncoder)]
  E --> F[⚖️ Scaling & Split\n(StandardScaler, train_test_split)]
  F --> G[🧠 Modeling\n(LogisticRegression, KNN, GaussianNB)]
  G --> H[📊 Evaluation\n(precision, recall, f1, accuracy, CM)]
  H --> I[🔁 Feature Engineering\n(add features, retrain)]
