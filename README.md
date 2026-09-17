# hospital-readmission-prediction

Case Study 1: Hospital Readmission Prediction — Use Logistic Regression with L2 regularization on patient records to predict 30-day readmission risk. Evaluate with ROC-AUC and discuss the clinical cost of false negatives vs. false positives.

# Hospital Readmission Prediction using Logistic Regression

A foundational machine learning pipeline designed to predict 30-day hospital readmission using patient records from the **UCI Diabetes 130-US Hospitals for Years 1999–2008** dataset.

## Project Overview

In healthcare analytics, predicting patient readmissions can help identify patients who may need additional follow-up. This project applies data preprocessing, feature scaling and L2-regularized Logistic Regression to classify readmission risk.

### Key Highlights

* **Dataset:** UCI Diabetes 130-US Hospitals for Years 1999–2008 containing **101,766 patient records** and **47 features**.
* **Target:** The `readmitted` field is used to identify patients readmitted within 30 days (`<30`).
* **Exploratory Data Analysis (EDA):** Inspected patient and hospital-related features and the readmission classes.
* **Feature Scaling:** Standardized numerical features before model training.
* **Modeling:** Trained a **Logistic Regression** model with **L2 regularization**.
* **Evaluation:** Used **ROC-AUC** and a confusion matrix to evaluate the model.

## Performance Metrics

Evaluation on the held-out 20% test split yielded the following predictive baseline performance:

* **ROC-AUC Score:** `0.6462`
* **Confusion Matrix:**

$$
\begin{bmatrix}
18039 & 44 \\
2229 & 42
\end{bmatrix}
$$

*(True Negatives: 18039 | False Positives: 44 | False Negatives: 2229 | True Positives: 42)*

## Project Structure

```text
├── CaseStudy1.ipynb
├── requirements.txt
└── data/
    └── README.md
```

## Getting Started & Replication

You can launch and run this notebook in Google Colab or Jupyter Notebook using the UCI Diabetes 130-US Hospitals dataset.

