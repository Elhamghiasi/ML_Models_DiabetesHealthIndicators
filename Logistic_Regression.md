## 2. Logistic Regression

### 2.a. Logistic Regression (No Regularization)

Before modeling, we first separated the features from the target variable and split the data into **training** and **test** sets. We also **scaled the features** to ensure fair contribution across variables.

**Results:**

- **Accuracy:** 0.8621  
- **Precision:** 0.5164  
- **Recall:** 0.1584  
- **F1 Score:** 0.2425  

While the accuracy of **86.2%** seems promising, the model struggles to correctly identify the positive class (diabetes cases). The **low recall (15.8%)** and **F1-score (24.2%)** suggest that the model is heavily affected by class imbalance and potentially by the absence of regularization.

---

### 2.b. Logistic Regression with L1 Regularization (Lasso)

We applied **L1 regularization** to the logistic regression model to see if it could improve performance by shrinking less useful features.

**Results:**

- **Accuracy:** 0.8621  
- **Precision:** 0.5164  
- **Recall:** 0.1584  
- **F1 Score:** 0.2425  

The results are **identical** to the model without regularization. This indicates that L1 did not significantly impact the model, possibly because the data was already sparse or the features not highly redundant.

---

### 2.c. Logistic Regression with L2 Regularization (Ridge)

Using **L2 regularization**, we aimed to address any potential overfitting or multicollinearity.

**Results:**

- **Accuracy:** 0.8621  
- **Precision:** 0.5171  
- **Recall:** 0.1583  
- **F1 Score:** 0.2424  

This model performed **almost identically** to the others. Regularization didn’t noticeably improve model performance, likely due to class imbalance and the structure of the data.

---

### 2.d. Comparison & Discussion

All three logistic regression models—**no regularization**, **L1 (Lasso)**, and **L2 (Ridge)**—performed similarly:

- Accuracy remained around **86.2%**
- Precision, recall, and F1-scores for **Class 1** were nearly the same

The **lack of improvement from regularization** suggests that the dataset may already be clean and well-structured, or that the features aren’t highly redundant. The **class imbalance** remains a key challenge, as recall for diabetes cases is consistently low.

To improve recall and better capture the minority class, we recommend trying:
- **Class weighting**
- **Oversampling techniques** (e.g., SMOTE)
- **Under-sampling the majority class**
