## 4. Neural Networks

### 4.a. Model A – Simple Neural Network

We started by designing a **simple feedforward neural network (Model A)** with one or two hidden layers. This model was evaluated on the test set and showed moderate performance:

- **Accuracy:** 0.8654  
- **Precision:** 0.5787  
- **Recall:** 0.1243  
- **F1 Score:** 0.2047  

Although the performance isn’t dramatically better than other models, we observed a **slight improvement in recall and F1-score**, indicating that even a basic neural network may detect some non-linear relationships in the data. However, the results are still affected by the **class imbalance**, limiting the model’s ability to effectively identify positive diabetes cases.

---

### 4.b. Model B – Deep Neural Network with Dropout

Next, we built **Model B**, a deeper neural network architecture that included **dropout layers** for regularization. This model also achieved an accuracy of **86.53%**.

- **Accuracy:** 0.8653  
- **Precision:** 0.5790  
- **Recall:** 0.1243  
- **F1 Score:** 0.2050  

While **precision slightly increased** and the **F1-score improved**, recall stayed almost the same. The inclusion of dropout likely helped reduce overfitting, but once again, the model struggled to identify positive cases due to the **persistent class imbalance**.

---

### Summary

Both neural network models (Model A and B) performed **similarly** to SVMs and logistic regression in terms of accuracy. The deeper architecture in Model B showed **minor improvements**, but neither model significantly overcame the challenges posed by class imbalance.
