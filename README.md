Project Overview: Semiconductor Manufacturing Failure Analysis
This project focuses on analyzing and improving the classification of pass/fail outcomes in semiconductor manufacturing data. The dataset is highly imbalanced, making it challenging to detect rare failure cases. The main goal is to evaluate how different preprocessing techniques (undersampling and SMOTE) and dimensionality reduction using PCA affect the performance of various classification models—Random Forest, SVM, and Naïve Bayes.

Techniques Applied:
Class Imbalance Handling:

Undersampling to reduce the majority class.

SMOTE (Synthetic Minority Oversampling Technique) to boost minority class instances.

Dimensionality Reduction:

Applied PCA with different component sizes (150 for undersampling, 3 for SMOTE).

Modeling:

Evaluated with Random Forest, SVM, and Naïve Bayes classifiers.

Metrics considered: Accuracy, F1-scores (for both classes), Precision, Recall, Macro/Weighted Averages.

Key Insights:
Random Forest:

Performed consistently well across scenarios.

PCA slightly improved overall accuracy but worsened minority class (failure) detection.

Best suited when SMOTE is not combined with PCA.

SVM:

Performed acceptably without PCA but completely failed after applying PCA in both undersampling and SMOTE setups.

Not recommended when using PCA.

Naïve Bayes:

Stable performance with or without PCA.

Slight improvement after PCA in SMOTE scenario but still underperforms overall compared to other models.

Recommendation:
Use Random Forest without PCA (after undersampling) for balanced performance.

Avoid using SVM with PCA due to severe performance degradation.

Naïve Bayes is stable and lightweight but not optimal in terms of classification strength.

For the detailed interpreations and conculsions of the project please refer to the interpreations.ipynb file 
