# Predictive Maintenance with Machine Learning

## Overview
This project applies Machine Learning techniques to predict equipment failures before they happen, enabling proactive maintenance and reducing operational downtime.

Using industrial sensor data, the objective is to classify whether a machine is likely to fail based on operational conditions such as torque, rotational speed, tool wear, and temperature measurements.

This project compares two classification models:
  - Logistic Regression
  - Random Forest

The goal is to evaluate which model better detects machine failures while minimizing false negatives (failure cases classified as normal), since these represent the highest business risk in predictive maintenance.

---

## Business Problem
Unexpected machine failures can generate:

  - Production downtime
  - Maintenance costs
  - Safety risks
  - Loss of operational efficiency

Predictive maintenance uses historical machine data to anticipate failures and optimize maintenance scheduling.

---

## Dataset
The dataset used is the **AI4I 2020 Predictive Maintenance Dataset** from Kaggle, containing simulated industrial machine data.

### Features
- Air temperature [K]
- Process temperature [K]
- Rotational speed [rpm]
- Torque [Nm]
- Tool wear [min]
- Machine type
- Failure indicators

### Target Variable
- `Machine failure`
    - 0 → No failure
    - 1 → Failure

---

## Project Pipeline

### 1. Data Understanding
- Initial dataset inspection
- Data types analysis
- Missing value verification
- Class imbalance analysis

### 2. Exploratory Data Analysis (EDA)
Exploratory analysis was performed to understand variable distributions and failure patterns.

Key analyses:
- Failure distribution
- Correlation matrix
- Feature distributions
- Relationship between sensor variables and failures

---

### 3. Data Preprocessing
Steps performed:

- Encoding categorical variables
- Feature scaling
- Train-test split

---

### 4. Model Training

Two supervised classification models were trained.

#### Logistic Regression
Chosen as a baseline model because of:
- Simplicity
- Interpretability
- Fast training

#### Random Forest
Chosen because:
- Captures non-linear patterns
- Robust to noise
- Provides feature importance

---

## Model Evaluation

Evaluation metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

### Model Comparison

| Metric | Logistic Regression | Random Forest |
|--------|---------------------|---------------|
| Accuracy | 0.97	 | 	0.98 |
| Precision | 0.60 | 0.86 |
| Recall | 0.13| 0.63 |
| F1-score | 0.22 | 0.73 |

---

## Confusion Matrix Insights

In predictive maintenance, **False Negatives are the most critical error**.

False Negative means:
- The model predicts **no failure**, but the machine actually fails.

Business impact:
- Unexpected breakdown
- Financial losses
- Unplanned maintenance

Therefore, **Recall** is particularly important in this use case.

---

## Feature Importance (Random Forest)

Top predictive features:

1. Torque
2. Rotational speed
3. Tool wear
4. Air temperature
5. Process temperature

These variables showed the highest contribution to failure prediction.

---

## Key Insights
- Random Forest outperformed Logistic Regression in failure detection.
- Torque was the most important predictive feature.
- Tree-based models (Random Forest) captured complex relationships better than linear models.
- In predictive maintenance, maximizing recall is often more important than maximizing accuracy.

---

## Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

---

## Repository Structure

```bash
predictive_maintenance/
│
├── predictive_maintenance_ml.ipynb
├── README.md
└── database
```
---

## Author
**Suzana Faria**

