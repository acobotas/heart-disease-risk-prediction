
# 10-Year Coronary Heart Disease (CHD) Risk Prediction

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Machine learning](https://img.shields.io/badge/Machine_Learning-0078D4?style=for-the-badge)
![Classification](https://img.shields.io/badge/Classification-C24945?style=for-the-badge)

*An end-to-end logistic regression project predicting the 10-year risk of coronary heart disease (CHD).

## Quick Links
* **Notebook:** Regression: Cardiovascular Disease Prediction
* **Dataset:** [Cardiovascular Study Dataset on Kaggle](https://www.kaggle.com/datasets/christofel04/cardiovascular-study-dataset-predict-heart-disea)

## Objectives
* Predict 10-year risk of CHD using logistic regression.
* Handle class imbalance using stratified splits and class weighting.
* Optimize model threshold for F2-Score to prioritize recall.
* Perform robust preprocessing and feature engineering based on EDA.

## Methodology
1. Data Cleaning & Preparation
2. Exploratory Data Analysis (EDA)
3. Feature Selection & Transformation (log-transform skewed features, remove multicollinear features)
4. Missing Value Imputation
5. Train/Test Split (stratified)
6. Logistic Regression with class_weight='balanced'
7. Threshold Optimization based on F2-Score
8. Model Evaluation (Recall, F2, ROC-AUC, Confusion Matrix)

## Key Insights
* Age, BMI, and systolic BP are strong predictors of CHD.
* Removing multicollinear features improved model stability.
* Log-transforming skewed features increased model performance.
* Optimized threshold increased F2 from 0.487 to 0.525 on test set.

## Future Improvements
* Use pipelines for preprocessing and modeling.
* Explore alternative models (e.g., XGBoost, LightGBM).
* Perform cost-sensitive threshold tuning based on false positive/negative costs.
* Conduct in-depth analysis on misclassified samples.
