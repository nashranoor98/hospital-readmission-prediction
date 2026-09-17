# hospital-readmission-prediction

Case Study 1: Hospital Readmission Prediction — Use Logistic Regression with L2 regularization on patient records to predict 30-day readmission risk. Evaluate with ROC-AUC and discuss the clinical cost of false negatives vs. false positives.

# Hospital Readmission Prediction using Logistic Regression

A machine learning pipeline designed to predict 30-day hospital readmission using patient records from the UCI Diabetes 130-US Hospitals dataset.

## Project Overview

The project applies data preprocessing, feature scaling and **Logistic Regression with L2 regularization** to classify patients based on whether they are readmitted within 30 days.

### Key Highlights

* **Dataset:** [UCI Diabetes 130-US Hospitals for Years 1999–2008](https://archive.ics.uci.edu/dataset/296/diabetes+130+us+hospitals+for+years+1999+2008)
* **Target:** `readmitted = <30` is treated as readmission within 30 days.
* **Preprocessing:** Missing-value handling, categorical encoding and feature scaling.
* **Modeling:** Logistic Regression with L2 regularization.
* **Evaluation:** ROC-AUC, classification report and confusion matrix.
* **Clinical Analysis:** Discussion of false negatives and false positives.

---

## Project Structure

```text
├── CaseStudy1.ipynb
├── README.md
└── .gitignore
```

---

## Getting Started

Download the UCI dataset and run `CaseStudy1.ipynb` in Jupyter Notebook or Google Colab.

> This project is an academic machine learning case study and is intended for educational purposes.
