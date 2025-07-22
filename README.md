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
### Problem Statement
Customer churn represents a major challenge for SyriaTel, with high churn rates directly impacting revenue and profitability. Traditional retention methods are inefficient and costly.

### Objectives
1. Predict churn probability with >90% accuracy
2. Identify key churn drivers
3. Recommend targeted retention strategies
4. Reduce churn rate by 30%

# Data Understanding
**Dataset:** 3,333 customer records with 20 features  
**Source:** [SyriaTel Customer Data](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset)  

**Target Variable:** `churn` (Binary: True/False)  

### Key Features:

| Category | Features |
|----------|----------|
| Account | `account_length`, `area_code` |
| Services | `international_plan`, `voice_mail_plan` |
| Usage | `total_day_minutes`, `total_night_charge` |
| Support | `customer_service_calls` |

## Data Preparation
### Cleaning Steps:
1. Removed `phone_number` (irrelevant identifier)
2. Encoded categorical features:
   - Label encoded `state` and `area_code`
   - One-hot encoded `international_plan` and `voice_mail_plan`
3. Standardized column names to snake_case
4. Addressed class imbalance with SMOTE oversampling

### Key Insights from EDA:
- **14.5% churn rate** (significant class imbalance)
- International plan subscribers churn **4.5× more**
- Churners have **18% higher daytime charges**
- Electronic check users churn **2.8× more**


