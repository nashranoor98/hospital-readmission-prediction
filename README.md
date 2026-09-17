# Hospital Readmission Prediction

**Case Study 1:** Use Logistic Regression with L2 regularization on patient records to predict **30-day hospital readmission risk**. Evaluate with **ROC-AUC** and discuss the clinical cost of false negatives vs. false positives.

## Project Overview

This project uses the **UCI Diabetes 130-US Hospitals for Years 1999–2008** dataset to build an educational machine-learning pipeline for predicting whether a patient will be readmitted within 30 days.

### Key Highlights

- **Dataset:** UCI Diabetes 130-US Hospitals for Years 1999–2008
- **Target:** `readmitted == "<30"`
- **Model:** Logistic Regression with **L2 regularization**
- **Preprocessing:** Missing-value imputation, one-hot encoding, and feature scaling
- **Evaluation:** ROC-AUC, classification report, confusion matrix, and ROC curve
- **Clinical discussion:** False-negative vs. false-positive trade-off

> **Note:** The UCI dataset does not contain a dedicated standardized vital-sign table. The notebook uses clinical measurements and utilization variables actually available in the dataset, including glucose/A1C indicators and prior outpatient/emergency/inpatient visits.

## Project Structure

```text
├── CaseStudy1.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── data/
    └── README.md
```

## Dataset Setup

The raw dataset is intentionally not committed to this repository. Download `diabetic_data.csv` from the UCI Machine Learning Repository and place it at `data/diabetic_data.csv`.

## Run

```bash
pip install -r requirements.txt
jupyter notebook CaseStudy1.ipynb
```

## Clinical Cost Discussion

A false negative is a patient who is actually readmitted within 30 days but is not flagged. A false positive is a patient who is flagged but is not readmitted within 30 days. False negatives can represent missed opportunities for follow-up, while false positives can consume care-team resources. The appropriate threshold therefore depends on the relative cost assigned to these errors.

**Educational case study only; not a clinical decision-support system.**
