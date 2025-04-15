## 3. Support Vector Machine (SVM) – Linear, Polynomial, RBF

In this section, we explored Support Vector Machine (SVM) models with different kernels. Due to the computational cost of SVC on large datasets, we used **LinearSVC** for the linear kernel (3a), and **SVC** with `poly` and `rbf` kernels for parts 3b and 3c, respectively. In part 3d, we compare the performance of all three models and discuss how **class imbalance** affected their results.

---

### 3.a. SVM with Linear Kernel

We used **LinearSVC** as a faster alternative for linear kernel SVM. The model achieved an accuracy of **86.27%**, similar to logistic regression. However, performance on the minority class was poor:

- **Accuracy:** 0.8627  
- **Precision:** 0.5573  
- **Recall:** 0.0695  
- **F1 Score:** 0.1235  

The **recall of only 6.95%** for positive diabetes cases indicates that the model misclassified most of them, clearly showing the impact of **class imbalance**.

---

### 3.b. SVM with Polynomial Kernel

Polynomial kernels tend to be slow on large datasets. To address this, we used a **sample of 10,000 training examples**. The model showed slightly better recall and F1-score than the linear kernel but still struggled overall.

- **Accuracy:** 0.8581  
- **Precision:** 0.4640  
- **Recall:** 0.1202  
- **F1 Score:** 0.1910  

Despite being more flexible, the polynomial kernel **did not significantly improve** the model’s ability to detect positive cases, and the training time was noticeably longer.

---

### 3.c. SVM with RBF Kernel (Sampled Data)

The **RBF kernel** is known for handling non-linear relationships, but performance on this dataset was still limited. Using sampled data:

- **Accuracy:** 0.8629  
- **Precision:** 0.5644  
- **Recall:** 0.0700  
- **F1 Score:** 0.1246  

The model had the **highest precision** of the three but **failed to improve recall**, again missing most positive diabetes cases due to class imbalance.

---

### 3.d. Comparison & Discussion

| Kernel      | Accuracy | Precision | Recall | F1 Score |
|-------------|----------|-----------|--------|----------|
| Linear      | 86.27%   | 55.73%    | 6.95%  | 12.35%   |
| Polynomial  | 85.81%   | 46.40%    | 12.02% | 19.10%   |
| RBF         | 86.29%   | 56.44%    | 7.00%  | 12.46%   |

- The **Linear kernel** was fastest but performed the worst in recall.
- The **Polynomial kernel** improved recall and F1 slightly but had longer training times.
- The **RBF kernel** achieved the best precision but didn't help much with detecting positives.

Across all three models, **class imbalance remained the biggest issue**. None of the kernels significantly improved recall for positive cases, which highlights the need for techniques like **resampling**, **class weighting**, or **SMOTE** to improve performance for the minority class.
