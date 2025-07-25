## SyriaTel Customer Churn Prediction

![Telecom Churn](images/customer%20churn.png)

**Author**: [Mathews Odongo](mailto:wandera59@gmail.com) 

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

![Churn Analysis](images/churn_distribution.jpg)

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

## .Machine Learning Modeling
### Models Trained:
- `Logistic Regression` (baseline)
- `Random Forest Classifier`
- `XGBoost Classifier` (best performer)

All models used pipelines with preprocessing and SMOTE for handling class imbalance.

### Techniques:
- Train-test split (80/20)
- GridSearchCV for hyperparameter tuning
- SMOTE for class imbalance
- Evaluation metrics:
  - Accuracy, Precision, Recall, F1-Score
  - ROC-AUC Curve
## Model Performance Comparison


| Model               | Accuracy | ROC-AUC | Precision | Recall | F1-Score |
|--------------------|----------|---------|-----------|--------|----------|
| Logistic Regression| ~85%     | 0.88    | 0.51      | **0.86** | 0.64     |
| Random Forest       | ~90%     | 0.91    | **0.81**  | 0.73   | 0.77     |
| XGBoost             | **94%**  | **0.93**| 0.77      | 0.85   | **0.81** |

---

###  Summary

- **XGBoost**: Best overall — high accuracy, balanced precision/recall. Ideal for deployment.
- **Random Forest**: Strong backup with good balance and interpretability.
- **Logistic Regression**: Most interpretable, high recall but lower precision — useful for insights.

## Feature Importance (XGBoost)

Top 5 Features:
1. `international_plan_yes`
2. `total_day_charge`
3. `customer_service_calls`
4. `total_day_minutes`
5. `voice_mail_plan_yes`
   
![Feature Importance](images/top%2015%20features%20XGBoost.jpg)

## Key Insights
- Customers with an international plan are significantly more likely to churn.
- Frequent customer service calls are strongly associated with churn.
- Daytime call usage and charges are predictive of dissatisfaction.

## Conclusion
The XGBoost model effectively predicts customer churn and identifies high-risk segments. These insights enable SyriaTel to take proactive steps in customer retention, especially targeting:
- High service callers
- International plan users
- High day-time usage customers



## License
MIT License 
This project is for educational purposes only.





