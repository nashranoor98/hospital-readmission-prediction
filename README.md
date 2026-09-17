# hospital-readmission-prediction

Case Study 1: Hospital Readmission Prediction — Use Logistic Regression with L2 regularization on patient records to predict 30-day readmission risk. Evaluate with ROC-AUC and discuss the clinical cost of false negatives vs. false positives.

# Hospital Readmission Prediction using Logistic Regression

A foundational machine learning pipeline designed to predict 30-day hospital readmission using patient records from the **UCI Diabetes 130-US Hospitals for Years 1999–2008** dataset.

## Project Overview

In healthcare analytics, predicting patient readmissions can help identify patients who may need additional follow-up. This project applies data preprocessing, feature scaling and L2-regularized Logistic Regression to classify readmission risk.

### Dataset

The project uses the **Diabetes 130-US Hospitals for Years 1999–2008** dataset from the UCI Machine Learning Repository.

**Dataset:** [UCI Machine Learning Repository — Diabetes 130-US Hospitals for Years 1999–2008](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008)

- **Instances:** 101,766
- **Features:** 47
- **Target:** `readmitted` — whether the patient was readmitted within 30 days (`<30`)

### Key Highlights

* **Exploratory Data Analysis (EDA):** Inspected patient and hospital-related features and the readmission classes.
* **Feature Scaling:** Standardized numerical features before model training.
* **Modeling:** Trained a **Logistic Regression** model with **L2 regularization**.
* **Evaluation:** Used **ROC-AUC** and a confusion matrix to evaluate the model.

## Performance Metrics

Evaluation on the held-out 20% test set:

- **ROC-AUC Score:** `0.6462`
- **Confusion Matrix:**

  $$
  \begin{bmatrix}
  18039 & 44 \\
  2229 & 42
  \end{bmatrix}
  $$

*(True Negatives: 18039 | False Positives: 44 | False Negatives: 2229 | True Positives: 42)*

## Clinical Cost Considerations

In this healthcare setting, a **false negative** means a patient who is actually readmitted within 30 days is predicted as low risk. Missing such patients may delay additional follow-up or preventive intervention. A **false positive** means a patient is flagged as high risk but is not actually readmitted, which may lead to additional monitoring or resource use.

## Project Structure

```text
├── CaseStudy1.ipynb
└── README.md
```

## Getting Started & Replication

You can launch and run this notebook in Google Colab or Jupyter Notebook using the UCI Diabetes 130-US Hospitals dataset.

