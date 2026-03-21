# Hospital Readmission Prediction Using Machine Learning

### Predicting Patient Readmission Risk Using Healthcare Data

---

## Project Overview

Hospital readmissions are costly and often preventable. This project uses machine learning to predict patient readmission risk using structured healthcare data.

---

## Problem Statement

The goal is to identify patients at high risk of readmission to support better care planning and resource allocation.

---

## Dataset

Diabetes 130-US Hospitals dataset

Features include:
- Patient demographics  
- Diagnoses  
- Hospital visits  

Target:
- Readmission (Yes/No)

---

## Preprocessing

- Data cleaning  
- Encoding categorical variables  
- Feature engineering  
- Train-test split  

---

## Models

- Logistic Regression  
- Decision Tree  
- Random Forest  

---

## Model Performance

| Model | Accuracy | Recall |
|------|--------|--------|
| Logistic Regression | ~0.75 | ~0.70 |
| Decision Tree | ~0.80 | ~0.78 |
| Random Forest | ~0.85 | ~0.82 |

---

## Key Findings

- Prior hospital visits strongly influence readmission  
- Age and diagnosis patterns are important predictors  
- Random Forest performs best due to nonlinear modeling  

---

## Why This Matters

This model helps hospitals:
- Identify high-risk patients  
- Improve care planning  
- Reduce readmission costs  

---

## Project Structure

- Capstone3_Preprocessing_Modeling_Readmission_final.ipynb  
- capstone3_metrics.csv
- project_proposal.pdf  
- hospital_readmission_capstone_report.docx
- hospital_readmission_capstone_presentation.pptx
- README.md  

---

## Future Work

- Add more clinical features  
- Improve model tuning  
- Deploy model for real-world use  
