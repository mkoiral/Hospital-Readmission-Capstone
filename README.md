# Hospital Readmission Prediction Using Machine Learning

## Project Overview

Hospital readmissions are a major challenge in healthcare systems, leading to increased costs and indicating potential gaps in patient care. Early identification of high-risk patients enables hospitals to intervene proactively and improve outcomes.

This project develops machine learning models to predict 30-day hospital readmission using the Diabetes 130-US Hospitals dataset. The goal is not only to build predictive models but also to understand the tradeoffs between different modeling approaches and their implications for real-world deployment.

---

## Problem Statement

Traditional healthcare systems rely on manual rules and limited statistical models to assess readmission risk. These approaches often fail to capture complex relationships between patient characteristics and outcomes.

The objective of this project is to:

- Predict whether a patient will be readmitted within 30 days
- Compare multiple machine learning models
- Identify key drivers of readmission risk
- Evaluate model performance under class imbalance
- Provide actionable insights for healthcare decision-making

---

## Dataset

- Source: UCI Diabetes 130-US Hospitals Dataset  
- Observations: 101,766 hospital encounters  
- Features: ~47 after preprocessing  
- Target:  
  - `1` → readmitted within 30 days  
  - `0` → not readmitted within 30 days  
- Class Imbalance: ~11% positive class  

The dataset includes:
- Demographics (age, gender, race)
- Clinical diagnoses
- Hospital utilization (inpatient visits, admissions)
- Medication and treatment variables

---

## Project Structure

```
capstone-readmission-project/
│
├── Capstone3_Preprocessing_Modeling_Readmission_final.ipynb
├── project_proposal.pdf
├── capstone3_metrics.csv
├── hospital_readmission_capstone_final_report.pdf
├── hospital_readmission_capstone_final_presentation.pptx
└── README.md
```

---

## Preprocessing & Feature Engineering

Key preprocessing steps include:

- Handling missing values (`?`) using imputation
- One-hot encoding categorical variables
- Standardizing numerical features
- Removing identifier columns to prevent data leakage
- Creating a binary target variable (`readmitted_30d`)
- Stratified train-test split to preserve class distribution

---

## Exploratory Data Analysis (EDA)

Key findings:

- Strong class imbalance → majority of patients are not readmitted
- Missing values concentrated in clinically relevant variables
- Healthcare utilization (prior visits) strongly correlates with readmission
- Multiple features interact → nonlinear modeling required

---

## Models Evaluated

### Logistic Regression (Baseline)
- Simple and interpretable
- Performs well in detecting minority class (high recall)
- Limited ability to capture nonlinear relationships

### Random Forest
- Captures nonlinear interactions
- High overall accuracy
- Very low recall for readmission cases

### Gradient Boosting (Final Model)
- Best ROC-AUC (0.679)
- Strong ranking ability
- Selected as final model

---

## Model Performance (Test Set)

| Model                | Accuracy | Recall | F1 Score | ROC-AUC |
|---------------------|----------|--------|----------|---------|
| Logistic Regression | 0.643    | 0.548  | 0.255    | 0.644   |
| Random Forest       | 0.889    | 0.005  | 0.010    | 0.663   |
| Gradient Boosting   | 0.888    | 0.007  | 0.015    | 0.679   |

---

## Key Findings

- Gradient Boosting provides the best **ranking performance**
- Logistic Regression provides the best **recall (detecting readmissions)**
- Tree-based models are **conservative** in predicting minority class
- High accuracy does NOT imply good detection of high-risk patients

---

## Critical Insight

The final model (Gradient Boosting):

- ❌ Performs poorly as a classifier at default threshold  
- ✅ Performs well as a **risk ranking model**

👉 This means:

- The model is useful for prioritizing patients  
- But not directly usable for binary decision-making without tuning  

---

## Visualizations Included

- Class distribution (imbalance)
- Missing value analysis
- ROC curve (model discrimination)
- Precision–Recall curve (performance under imbalance)
- Confusion matrix (classification behavior)

---

## Recommendations

- Use model for **risk stratification**, not direct classification
- Adjust decision threshold based on hospital capacity
- Prioritize patients with highest predicted risk
- Integrate model into clinical decision-support systems

---

## Limitations

- Severe class imbalance affects recall
- Limited feature set (no temporal or longitudinal data)
- Default threshold not optimized
- Model not yet deployment-ready

---

## Future Work

- Threshold tuning and calibration
- Cost-sensitive learning
- Advanced models (XGBoost, LightGBM)
- Incorporate longitudinal patient data
- Apply SHAP for model interpretability

---

## Why This Matters

This project demonstrates that:

- Machine learning models can improve healthcare decision-making
- Model evaluation must go beyond accuracy in imbalanced datasets
- Ranking-based approaches are often more practical in real-world scenarios

---



## Author


Capstone Project – Springboard Data Science Program by Mahesh Koirala
