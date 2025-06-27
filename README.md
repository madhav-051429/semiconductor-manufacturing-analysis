# 🔍 Project Overview: Semiconductor Manufacturing Failure Analysis

This project focuses on analyzing and improving the classification of pass/fail outcomes in semiconductor manufacturing. The dataset is highly imbalanced, making it challenging to detect rare failure cases. The goal is to evaluate how different preprocessing techniques and dimensionality reduction using PCA affect the performance of various classifiers.

---

## 🛠️ Techniques Applied

- **Class Imbalance Handling**  
  - 🔹 **Undersampling** (to reduce majority class)
  - 🔹 **SMOTE** (Synthetic Minority Oversampling Technique)
  
- **Dimensionality Reduction**  
  - 🔹 Applied **PCA**
    - 150 components for undersampling scenario
    - 3 components for SMOTE scenario

- **Models Used**  
  - 🌲 **Random Forest**
  - 🧠 **Support Vector Machine (SVM)**
  - 📊 **Naïve Bayes**

- **Evaluation Metrics**
  - Accuracy
  - F1-score (Class -1 and Class 1)
  - Precision and Recall
  - Macro and Weighted Averages

---

## 📈 Key Insights

### 🔹 Random Forest
- Performed best overall across most configurations.
- PCA **slightly improved accuracy**, but **worsened minority class** (failure) detection.
- Best results observed **without PCA** in the SMOTE scenario.

### 🔹 SVM
- Performed **reasonably well before PCA**, but
- **Severely degraded after PCA** in both undersampling and SMOTE.
- **Not recommended** when PCA is involved.

### 🔹 Naïve Bayes
- Remained **stable** across all scenarios.
- Slightly improved with PCA in SMOTE.
- However, still **underperforms** compared to Random Forest.

---

## ✅ Final Recommendations

- ✅ Use **Random Forest without PCA (with SMOTE or Undersampling)** for balanced results.
- ❌ **Avoid using SVM with PCA** — results are highly unreliable.
- ⚠️ **Naïve Bayes** is stable but not ideal for detecting minority class failures.

---

## 📁 Summary Table (Selected Metrics)

| Model          | Scenario                     | Accuracy | Class -1 F1 | Class 1 F1 | Macro F1 |
|----------------|------------------------------|----------|-------------|------------|----------|
| Random Forest  | Undersampling, No PCA        | 74%      | 0.84        | 0.26       | 0.55     |
| Random Forest  | Undersampling, PCA (150)     | 76%      | 0.86        | 0.19       | 0.53     |
| Random Forest  | SMOTE, PCA (3)               | 79%      | 0.88        | 0.13       | 0.50     |
| SVM            | Undersampling, No PCA        | 60%      | 0.74        | 0.18       | 0.46     |
| SVM            | Undersampling, PCA (150)     | 07%      | 0.01        | 0.13       | 0.07     |
| SVM            | SMOTE, PCA (3)               | 52%      | 0.67        | 0.16       | 0.41     |
| Naïve Bayes    | Undersampling, No PCA        | 89%      | 0.94        | 0.22       | 0.58     |
| Naïve Bayes    | Undersampling, PCA (150)     | 89%      | 0.94        | 0.15       | 0.55     |
| Naïve Bayes    | SMOTE, PCA (3)               | 33%      | 0.45        | 0.15       | 0.30     |

---

> 📌 **Note**: For detailed analysis and plots, see the [`Interpretations.ipynb`](./Interpretations.ipynb) file.
