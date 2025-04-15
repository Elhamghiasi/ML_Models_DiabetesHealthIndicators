## Observations

### 1. Exploratory Data Analysis

#### 1.a. Dataset Overview

First, we load the dataset, explore its dimensions, and check for any missing values.

- The dataset contains **253,680 rows** and **22 columns**.
- Each row represents an individual's survey response.
- Each column corresponds to a health indicator, including the target variable `Diabetes_binary`.
-  **No missing values** were found in the dataset.
- All entries are **clean and numeric**.

#### 1.b. Target Variable Balance

We calculated the distribution of the target variable `Diabetes_binary`:

- **86.07%** of the entries are labeled as **"No diabetes"** (`0`)
- **13.93%** of the entries are labeled as **"Diabetes or prediabetes"** (`1`)

This shows a clear **class imbalance**, with most data points belonging to the majority class. Such imbalance can negatively impact model performance, particularly in predicting the minority class.

#### 1.c. Class Distribution Visualization

We visualized the class distribution using bar plots:

- The bar plot confirms the **imbalance** — the number of samples in the **"No diabetes"** group is significantly higher than the **"Diabetes/prediabetes"** group.
- This skewed distribution may make it more difficult for models to **learn from the minority class**, potentially reducing prediction accuracy for those cases.
