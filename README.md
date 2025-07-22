# # SyriaTel Customer Churn Prediction

![Telecom Churn Analysis](images/telcomimage.jpg)

## Overview
This project develops a machine learning solution to predict customer churn for SyriaTel, a telecommunications company. By analyzing historical customer data, we identify at-risk customers and provide actionable retention strategies to reduce churn rates and improve profitability

**Key Deliverables:**
- XGBoost model with 0.93 ROC-AUC score
- Identified top churn drivers and customer segments
- Actionable retention strategies
- 30% potential reduction in churn rate
  
### Business Understanding
- **Goal**: Minimize churn rate by identifying customers likely to leave.
- **Value**: Enables proactive customer retention campaigns
### Problem Statement
Customer churn represents a major challenge for SyriaTel, with high churn rates directly impacting revenue and profitability. Traditional retention methods are inefficient and costly.

# Data Understanding
**Dataset:** 3,333 customer records with 20 features  
**Source:** [SyriaTel Customer Data](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset)  
 **Target**: `churn` (binary: 0 = stayed, 1 = churned)
 **Features**:
  - Usage metrics (e`total_day_minutes`, `total_intl_charge`)
  - Subscription info (`international_plan`, `voice_mail_plan`)
  - Service interactions (`customer_service_calls`)
  - 
**Target Variable:** `churn` (Binary: True/False)  

## Data Cleaning & Preparation

- Removed duplicates and constant columns
- Addressed class imbalance via SMOTE
- Encoded categorical features using pipelines
- Removed highly correlated features (`total_day_charge` and `total_day_minutes`)

## Exploratory Data Analysis (EDA)

- Churn rate: ~14.5% (class imbalance)
- Key churn indicators:
  - High `customer_service_calls`
  - Presence of `international_plan`
  - High `total_day_charge`
- Statistical tests:
  - **T-test** and **Chi-square** to identify significant features
    
### Machinelearning Modeling
### Models Used:
- **Logistic Regression**
- **Random Forest**
- **XGBoost (Best performer)**


