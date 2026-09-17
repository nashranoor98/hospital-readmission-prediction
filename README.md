# hospital-readmission-prediction

**Case Study 1: Hospital Readmission Prediction** — Use Logistic Regression with L2 regularization on patient records to predict **30-day hospital readmission risk**. Evaluate the model with **ROC-AUC** and discuss the clinical cost of false negatives versus false positives.

# Hospital Readmission Prediction using Logistic Regression

A machine learning pipeline designed to predict whether a patient with diabetes will be **readmitted to a hospital within 30 days**. The project uses the **UCI Diabetes 130-US Hospitals for Years 1999–2008** dataset and applies preprocessing, feature transformation, and L2-regularized Logistic Regression for binary classification.

## Project Overview

Predicting early hospital readmission can help healthcare teams identify patients who may require additional follow-up and support after discharge. This project processes real-world hospital encounter records and builds a reproducible classification pipeline for early readmission prediction.

### Key Highlights

- **Dataset:** [UCI Diabetes 130-US Hospitals for Years 1999–2008](https://archive.ics.uci.edu/dataset/296/diabetes%2B130-us%2Bhospitals%2Bfor%2Byears%2B1999-2008), containing **101,766 hospitalized patient records** and **47 features** collected from 130 US hospitals and integrated delivery networks.
- **Prediction Target:** Converted the original `readmitted` field into a binary target where `"<30"` represents readmission within 30 days.
- **Clinical Features:** Uses available patient and hospital information such as diagnoses, laboratory-related indicators, medications, time in hospital, and prior outpatient, emergency, and inpatient visits.
- **Data Preprocessing:** Handles missing values, removes identifier/highly incomplete columns, encodes categorical variables, and scales numerical features using `StandardScaler`.
- **Modeling:** Trains a `LogisticRegression` model with **L2 regularization** to control model complexity and reduce overfitting.
- **Evaluation:** Uses **ROC-AUC, classification report, confusion matrix, and ROC curve** to evaluate predictive performance.
- **Clinical Error Analysis:** Discusses the different implications of false negatives and false positives in the context of hospital readmission screening.

> **Dataset note:** The UCI dataset does not provide a dedicated standardized vital-sign table. The project therefore uses the clinical measurements and healthcare-utilization variables that are actually available in the dataset rather than claiming unsupported vital-sign fields.

---

## Dataset

The project uses the official **UCI Machine Learning Repository** dataset:

**Diabetes 130-US Hospitals for Years 1999–2008**  
https://archive.ics.uci.edu/dataset/296/diabetes%2B130-us%2Bhospitals%2Bfor%2Byears%2B1999-2008

The dataset represents ten years of clinical care from 130 US hospitals. Each record corresponds to a hospitalized patient diagnosed with diabetes, with information covering diagnoses, laboratory tests, medications, hospital stay, and previous healthcare utilization.

The original `readmitted` variable contains three categories:

- `<30` — readmitted within 30 days
- `>30` — readmitted after 30 days
- `NO` — not readmitted

For this case study, the target is converted to a binary classification problem:

```python
(readmitted == "<30").astype(int)
```

---

## Methodology

```text
UCI Hospital Records
        ↓
Data Loading & Cleaning
        ↓
Missing-Value Handling
        ↓
Feature Selection & Encoding
        ↓
Numerical Feature Scaling
        ↓
Stratified Train/Test Split
        ↓
L2-Regularized Logistic Regression
        ↓
Probability Prediction
        ↓
ROC-AUC & Classification Metrics
        ↓
Confusion Matrix / ROC Curve
```

---

## Model

The project uses **Logistic Regression with L2 regularization**.

L2 regularization adds a penalty on large model coefficients, helping control model complexity and reduce overfitting. The implementation uses scikit-learn's `LogisticRegression` with the `l2` penalty.

---

## Evaluation

The model is evaluated on a held-out test set using:

- **ROC-AUC** — measures how well the model separates patients who are readmitted within 30 days from those who are not.
- **Classification Report** — provides precision, recall, and F1-score.
- **Confusion Matrix** — shows true negatives, false positives, false negatives, and true positives.
- **ROC Curve** — visualizes the trade-off between true-positive rate and false-positive rate across classification thresholds.

Run `CaseStudy1.ipynb` to generate the actual evaluation results for the dataset.

---

## Clinical Cost Discussion

A **false negative** occurs when a patient who is actually readmitted within 30 days is not flagged by the model. In a healthcare screening context, this can represent a missed opportunity for additional follow-up.

A **false positive** occurs when the model flags a patient who is not readmitted within 30 days. This may lead to additional care-team attention or resource use.

Therefore, the acceptable balance between false negatives and false positives depends on the intended clinical workflow and the relative cost assigned to each type of error.

---

## Project Structure

```text
├── CaseStudy1.ipynb         # Complete end-to-end Jupyter Notebook pipeline
├── README.md                # Project documentation
├── requirements.txt         # Python dependencies
├── .gitignore               # Excludes raw datasets and temporary files
└── data/
    └── README.md            # Dataset download and placement instructions
```

---

## Getting Started & Replication

### 1. Download the dataset

Download `diabetic_data.csv` from the official UCI Machine Learning Repository and place it inside the `data/` directory:

```text
data/diabetic_data.csv
```

The raw dataset is intentionally **not committed to this repository**.

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook CaseStudy1.ipynb
```

You can also open the notebook in Google Colab after uploading the dataset according to the path expected by the notebook.

---

## Requirements

- Python 3.9+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- Jupyter Notebook

---

## Disclaimer

This repository is an **academic machine learning case study**. The model is intended for educational and analytical purposes and is **not a clinical decision-support system**.
