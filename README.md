# 10-Year Coronary Heart Disease (CHD) Risk Prediction

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Machine learning](https://img.shields.io/badge/Machine_Learning-0078D4?style=for-the-badge)
![Classification](https://img.shields.io/badge/Classification-C24945?style=for-the-badge)

An end-to-end logistic regression project predicting the 10-year risk of coronary heart disease (CHD).

## Quick Links
* ➡️ **View the Jupyter Notebook on GitHub**: [chd-risk-prediction-logit.ipynb](notebook.ipynb)
* **Dataset:** [Cardiovascular Study Dataset on Kaggle](https://www.kaggle.com/datasets/christofel04/cardiovascular-study-dataset-predict-heart-disea)

## Problem & Solution

**Problem:** CHD is a leading cause of death, and early identification of high-risk patients can save lives and reduce healthcare costs.  

**Solution:** Built a logistic regression model to predict 10-year CHD risk using patient data. Optimized the decision threshold for F2-score to prioritize recall, ensuring high-risk patients are identified.

## Objectives
* Predict 10-year risk of CHD using logistic regression.
* Handle class imbalance using stratified splits and class weighting.
* Optimize model threshold for F2-Score to prioritize recall.
* Perform robust preprocessing and feature engineering based on Exploratory Data Analysis (EDA).

## Methodology
1. Data Cleaning & Preparation  
2. Exploratory Data Analysis (EDA)  
3. Feature Selection & Transformation (log-transform skewed features, remove multicollinear features)  
4. Missing Value Imputation  
5. Train/Test Split (stratified)  
6. Logistic Regression with `class_weight='balanced'`  
7. Threshold Optimization based on F2-Score  
8. Model Evaluation (Recall, F2, ROC-AUC, Confusion Matrix)  

## Threshold Optimization (F2-Score)

Because missing a high-risk patient is more costly than a false alarm, the decision threshold was optimized using the **F2-score**, which prioritizes recall over precision. The optimal threshold was selected based on training-set probabilities.

![F2 Threshold Optimization](images/threshold.png)

Lowering the threshold from 0.50 to 0.40 increased the model’s ability to identify at-risk patients while maintaining acceptable precision.

## Model Performance & Evaluation

### Confusion Matrix

The confusion matrix below illustrates model performance on the test set using the optimized threshold. The model favors recall, resulting in fewer false negatives at the expense of increased false positives — an appropriate trade-off for a medical screening task.

![Confusion Matrix](images/confusion_matrix.png)

### ROC Curve

The ROC curve (Receiver Operating Characteristic curve) visualizes the model's ability to distinguish between patients who will develop CHD and those who will not across all possible thresholds.

- **ROC-AUC (Area Under the ROC Curve):** 0.694  
  This metric summarizes the model’s overall discriminatory power.  
  * **1.0** = perfect separation of classes  
  * **0.5** = no better than random guessing  
  A ROC-AUC of 0.694 indicates the model reasonably separates at-risk and not-at-risk patients, showing it performs better than chance at predicting 10-year CHD risk.

![ROC Curve](images/roc_curve.png)

## Key Insights & Conclusions

- **F2 Score:** The initial model had an F2 score of **0.487** on the test set. After threshold optimization, the F2 score increased to **0.525**, an improvement of approximately **7.8%**, reflecting better detection of at-risk patients while maintaining a balance between recall and precision.  

- **Recall:** With the optimized threshold, the model achieved a **recall of ~80%**, meaning it correctly identifies 8 out of 10 patients who will develop CHD within 10 years. This high recall is crucial for a screening tool where missing at-risk patients carries significant consequences.  

- **ROC-AUC:** The model achieved a **ROC-AUC of 0.694**, indicating it can reasonably distinguish between patients who will and will not develop CHD over 10 years.

## Future Improvements
* Use pipelines for preprocessing and modeling.
* Explore alternative models (e.g., XGBoost, LightGBM).
* Perform cost-sensitive threshold tuning based on false positive vs. false negative impact.
* Conduct in-depth analysis on misclassified samples.