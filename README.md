# Comparative Machine Learning for Clinical Disease Prediction

A rigorous comparative machine learning study developing supervised classification pipelines for two clinical disease prediction tasks: **Breast Cancer Diagnosis** and **Heart Disease Prediction**.

---

## 📌 Project Overview
In medical machine learning, high accuracy alone is not sufficient. Reliable clinical AI models require strict prevention of data leakage, robust cross-validation, and clinical evaluation metrics beyond standard accuracy (such as Sensitivity, Specificity, and ROC-AUC). 

This project implements and compares three classical machine learning algorithms across two distinct tabular medical datasets.

---

## 📂 Datasets
1. **Breast Cancer Wisconsin (Diagnostic) Dataset (`data.csv`):** 
   - **Task:** Classify breast masses as *Malignant (M)* or *Benign (B)*.
   - **Features:** 30 numerical morphological features (mean, standard error, and worst values).
2. **Cleveland Heart Disease Dataset (`heart_cleveland_upload.csv`):**
   - **Task:** Predict the presence or absence of heart disease (*Condition 0 vs 1*).
   - **Features:** 13 clinical variables (age, sex, cholesterol, resting blood pressure, max heart rate, etc.).

---

## 🛠️ Methodology & Rigorous Practices
To ensure high standards of reproducibility and clinical reliability, the pipeline incorporates:
* **Data Leakage Prevention:** All feature scaling (`StandardScaler`) and modeling are combined inside `scikit-learn Pipeline` objects, ensuring preprocessing is fitted *exclusively* on training folds.
* **Stratified Splitting:** 80/20 stratified train-test splits to preserve class distributions.
* **Cross-Validation:** 5-fold stratified cross-validation performed strictly on the training set.
* **Hyperparameter Tuning:** Optimized using `GridSearchCV` targeting ROC-AUC.

---

## 🤖 Evaluated Models
* **Logistic Regression:** Serves as a transparent and interpretable linear baseline.
* **Random Forest:** Captures non-linear relationships and provides feature importance rankings.
* **Support Vector Machine (SVM):** Employs an RBF kernel to handle complex decision boundaries.

---

## 📊 Summary of Results

| Dataset | Model | Accuracy | Sensitivity | Specificity | ROC-AUC |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **Breast Cancer** | Logistic Regression | 0.965 | 0.929 | 0.986 | 0.996 |
| **Breast Cancer** | Random Forest | 0.974 | 0.929 | 1.000 | 0.993 |
| **Breast Cancer** | **SVM** | **0.974** | **0.929** | **1.000** | **0.995** |
| **Heart Disease** | **Logistic Regression** | **0.917** | **0.821** | **1.000** | **0.953** |
| **Heart Disease** | Random Forest | 0.883 | 0.786 | 0.969 | 0.940 |
| **Heart Disease** | SVM | 0.900 | 0.786 | 1.000 | 0.940 |

---

## 🔍 Explainability & Feature Importance
Using **Random Forest Feature Importance**:
* **Breast Cancer Top Predictors:** `area_worst`, `concave points_worst`, `radius_worst`, and `perimeter_worst` (aligning with clinical indicators of tumor morphology and size).
* **Heart Disease Top Predictors:** `thalach` (maximum heart rate), `cp` (chest pain type), `ca` (number of major vessels), and `oldpeak` (ST depression).

---

## 🚀 Tech Stack
* **Language:** Python
* **Libraries:** Scikit-learn, Pandas, NumPy, Matplotlib, Seaborn

---

## 📄 Documentation
A detailed academic report of this study is available in the repository as `AI_for_Medicine_Saeed_Gharani.pdf`.
