# 💳 Credit Risk Analytics using Machine Learning

### Predicting Borrower Default using Explainable Machine Learning

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-Gradient%20Boosting-green)
![SHAP](https://img.shields.io/badge/Explainability-SHAP-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Project Overview

Financial institutions must accurately assess the probability that a borrower will default before approving a loan. Poor credit decisions can lead to substantial financial losses, while overly conservative lending policies may reject financially reliable customers.

This project develops an end-to-end machine learning pipeline to predict whether a borrower will experience **serious delinquency within the next two years** using historical financial information.

Beyond predictive modeling, the project emphasizes:

- Robust exploratory data analysis
- Data leakage prevention
- Explainable AI using SHAP
- Model comparison
- Business interpretation
- Confidence-based deployment strategy

---

## 🎯 Business Objective

Develop a credit risk model capable of estimating borrower default probability while maintaining a balance between identifying risky applicants and minimizing false alarms.

Potential applications include:

- Loan approval support
- Credit card risk assessment
- Consumer lending
- Retail banking
- Risk analytics

---

# 🔄 Project Workflow

```
Dataset
    │
    ▼
Data Inspection
    │
    ▼
Exploratory Data Analysis
    │
    ▼
Data Preparation
    │
    ▼
Feature Engineering
    │
    ▼
Model Development
    │
    ▼
Model Evaluation
    │
    ▼
SHAP Explainability
    │
    ▼
Business Insights
```

---

# 📂 Dataset

**Source**

Give Me Some Credit (Kaggle)

**Target Variable**

SeriousDlqin2yrs

Binary Classification

- 0 → No Default
- 1 → Default

The dataset contains borrower demographic and financial attributes including:

- Age
- Monthly Income
- Debt Ratio
- Revolving Credit Utilization
- Number of Open Credit Lines
- Previous Delinquencies
- Number of Dependents

---

# 📊 Exploratory Data Analysis

The following analyses were performed:

- Dataset inspection
- Missing value analysis
- Summary statistics
- Target class distribution
- Histograms
- Boxplots
- Correlation heatmap
- Skewness analysis
- Outlier detection

## Key Findings

- Severe class imbalance (~6–7% defaults)
- MonthlyIncome contained approximately 20% missing values
- Several financial variables exhibited heavy right-skew
- Delinquency-related variables showed strong correlation
- No single feature exhibited strong linear predictive power

---

# ⚙️ Data Preparation

The preprocessing pipeline included:

- Train-test split prior to preprocessing to eliminate data leakage
- Median imputation using training statistics only
- Missing-value indicator for MonthlyIncome
- Log transformation of highly skewed variables
- Feature scaling for Logistic Regression
- Class weighting for imbalanced learning
- Threshold optimization
- Stratified sampling
- K-Fold Cross Validation

---

# 🤖 Machine Learning Models

Three supervised learning algorithms were evaluated.

| Model | Purpose |
|--------|----------|
| Logistic Regression | Interpretable baseline |
| Random Forest | Ensemble bagging model |
| XGBoost | Gradient boosting model |

---

# 📈 Evaluation Metrics

Performance was assessed using multiple complementary metrics.

- Accuracy
- Precision
- Recall
- Specificity
- F1 Score
- ROC-AUC
- PR-AUC
- Matthews Correlation Coefficient (MCC)
- Log Loss
- Brier Score
- Confusion Matrix

Threshold optimization was additionally performed to maximize F1-score.

---

# 🏆 Results

Among the evaluated models,

**XGBoost achieved the strongest overall predictive performance**, outperforming Logistic Regression and Random Forest across most evaluation metrics.

The comparison demonstrated that tree-based ensemble methods were better suited to this structured financial dataset than linear models.

---

# 🔍 Model Explainability

SHAP (SHapley Additive exPlanations) was used to interpret model predictions.

The explainability analysis identified the most influential features contributing to borrower default risk and provided both:

- Global feature importance
- Local prediction explanations

This enables transparent and interpretable credit risk assessment.

---

# 💼 Business Insights

Key observations from the analysis include:

- Previous payment delinquencies were among the strongest predictors of future default.
- High revolving credit utilization significantly increased borrower risk.
- High debt burden was associated with increased default probability.
- Missing income information itself contained predictive value.
- Default risk was driven by multiple interacting financial variables rather than any single feature.

---

# 🚀 Deployment Considerations

Although XGBoost achieved the strongest overall performance, the model was **not considered suitable for fully automated lending decisions**.

A more practical deployment strategy would involve:

- Predicting default probabilities
- Automatically processing high-confidence predictions
- Routing uncertain applications to manual underwriting

This human-in-the-loop workflow better aligns with real-world banking practices.

---

# 🛠 Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- XGBoost
- SHAP

---

# 📁 Repository Structure

```
Credit-Risk-Analytics/

│── README.md
│── requirements.txt
│── notebooks/
│     Credit_Risk_Analytics.ipynb
│
│── images/
│── docs/
│── results/
```

---

# 📌 Future Improvements

Potential extensions include:

- Hyperparameter optimization
- Feature engineering
- CatBoost and LightGBM comparison
- Probability calibration
- External validation datasets
- Model monitoring and drift detection

---

# 🎓 Key Takeaway

This project demonstrates a complete machine learning workflow for credit risk prediction, covering data inspection, exploratory data analysis, preprocessing, model development, evaluation, explainability and business interpretation.

While XGBoost achieved the strongest predictive performance, the available borrower attributes were insufficient for fully automated lending decisions. The results suggest that a confidence-based decision support system combined with human underwriting would be a more practical deployment strategy than binary loan approval or rejection.
