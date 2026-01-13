# Credit Default Risk Prediction Using Machine Learning

##  Project Overview

This project addresses the problem of **credit default risk prediction** using real-world consumer credit data. The objective is to determine whether a borrower is likely to experience **serious delinquency (90 or more days past due)** within a two-year period. This problem is central to credit risk management in banking and financial services and is characterized by class imbalance and behavioral uncertainty.

The project emphasizes robust preprocessing, careful model evaluation, and business-aware interpretation of results rather than relying solely on accuracy.

---

##  Dataset Description

The project uses the **Give Me Some Credit** dataset, where each observation corresponds to an individual borrower.

### Target Variable

* **SeriousDlqin2yrs**

  * `0`: Non-defaulter (no serious delinquency)
  * `1`: Defaulter (90+ days past due within two years)

### Input Features

The dataset includes demographic, financial, and credit behavior variables such as:

* Age and number of dependents
* Monthly income and debt ratio
* Credit utilization
* Number of open credit lines and loans
* Historical delinquency counts (30–59 days, 60–89 days, and 90+ days late)

The dataset is highly imbalanced, with approximately **93% non-defaulters** and **7% defaulters**, which closely reflects real-world credit risk distributions.

---

##  Data Preprocessing

The following preprocessing steps were applied to ensure reliable model performance:

* Missing value imputation using mean strategy
* Outlier treatment through percentile-based capping (1st–99th percentile)
* Feature scaling using Min–Max normalization
* Feature selection using Recursive Feature Elimination (RFE)
* Class imbalance handling using SMOTE (Synthetic Minority Oversampling Technique)

These steps help reduce noise, address skewed distributions, and improve model generalization.

---

## Modeling Approach

Multiple machine learning models were trained and compared to evaluate their suitability for credit default prediction:

* Logistic Regression
* Decision Tree
* Random Forest
* Gradient Boosting
* XGBoost
* LightGBM

Stratified cross-validation was used to preserve class proportions during training and evaluation. Hyperparameter tuning was applied to ensemble models to improve performance stability and generalization.

---

## Evaluation Metrics

Given the imbalanced nature of the dataset, model performance was assessed using multiple metrics:

* ROC–AUC (primary evaluation metric)
* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* ROC Curves

ROC–AUC was emphasized as it measures the model’s ability to **rank defaulters above non-defaulters across all classification thresholds**, which is critical in credit risk modeling.

---

##  Results and Model Selection

Most models achieved ROC–AUC values in the range of **0.85–0.86**, indicating strong discriminatory power. Among them, **LightGBM** demonstrated the best overall balance between accuracy, precision, and F1-score.

LightGBM achieved a **test accuracy of 92.8%** while maintaining strong ROC–AUC and the most favorable precision–recall trade-off. Confusion matrix analysis showed that the model is conservative in predicting defaults, reducing false positives while retaining reasonable recall, which is desirable in practical credit risk scenarios.

---

##  Interpretation and Insights

Credit default prediction is inherently challenging due to class imbalance and uncertainty in future borrower behavior. Rather than maximizing accuracy alone, this project prioritizes ranking quality and balanced decision-making.

The results demonstrate that ensemble models, particularly LightGBM, are effective in capturing complex risk patterns while providing stable and interpretable performance suitable for real-world credit decision systems.

---

##  Key Takeaways

* Credit default prediction is a realistic and high-impact machine learning problem
* ROC–AUC is a more reliable metric than accuracy for imbalanced financial data
* Ensemble methods outperform traditional baseline models
* LightGBM provides the best balance between performance and practical usability
* Proper preprocessing and evaluation are critical for trustworthy credit risk models

---

## Skills Demonstrated

* Data preprocessing and feature engineering
* Handling imbalanced classification problems
* Model comparison and performance evaluation
* Ensemble learning using XGBoost and LightGBM
* Business-aware interpretation of machine learning results


