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

The model is evaluated on a held-out test set using ROC-AUC and a confusion matrix. The exact performance values are generated when `CaseStudy1.ipynb` is executed with the dataset.

## Project Structure

```text
├── CaseStudy1.ipynb
└── README.md
```

## Getting Started & Replication

You can launch and run this notebook in Google Colab or Jupyter Notebook using the UCI Diabetes 130-US Hospitals dataset.

> This project is an academic machine learning case study intended for educational purposes.
