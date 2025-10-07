##  L1-Regularized Logistic Regression on Golub Leukemia Dataset

###  Project Overview

This project reproduces and analyzes the classic **Golub leukemia dataset (ALL vs AML)** using an **L1-regularized Logistic Regression model (LASSO)**.
 The goal is to identify **key gene expression features** that distinguish Acute Lymphoblastic Leukemia (ALL) from Acute Myeloid Leukemia (AML), and to evaluate the model’s diagnostic performance using ROC and cross-validation metrics.

------

###  Dataset

- **Source:** Golub et al., *Science*, 1999
- **Samples:** 72 total (38 for training, 34 for testing)
- **Features:** 3051 gene expression probes
- **Classes:** `ALL` and `AML`

------

###  Analysis Workflow

#### Step 1. Load and inspect data

The Golub training and test datasets were loaded and inspected for dimensions and label balance.

#### Step 2. L1-Regularized Logistic Regression (LASSO)

A Logistic Regression model with L1 penalty was fitted to identify informative genes.
 23 non-zero features were selected, representing the most discriminative gene probes.

**Example of selected genes:**

```
M27891_at, X95735_at, Y12670_at, M23197_at, M83652_s_at, ...
```

#### Step 3. Model Evaluation

Performance was assessed on the independent test set:

- **Confusion Matrix:**

  [[19  1]
   [ 0 14]]
  
- **Accuracy:** 0.97

- **AUC (test):** 1.00

- **5-fold CV AUC (mean):** 0.94

The model achieved excellent classification accuracy and stability, showing clear distinction between ALL and AML samples.

#### Step 4. Feature Coefficient Visualization

Feature coefficients were visualized to highlight the relative contribution of selected genes.
 Most coefficients were small, but a few (e.g., *M27891_at*) had strong positive influence on AML prediction.

------

###  Results Summary

- L1 regularization reduced dimensionality from 3051 to 23 genes.
- The final model achieved **97% accuracy** and **AUC = 1.0** on the test set.
- Selected genes may serve as potential biomarkers for leukemia subtype classification.

------

###  Key Insights

A simple model doesn’t mean limited performance.
With L1 regularization for feature selection, logistic regression achieved both high accuracy and strong interpretability, highlighting the practical value of traditional statistical models in bioinformatics.