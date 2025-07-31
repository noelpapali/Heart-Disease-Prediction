# Heart Disease Prediction Model 💓 

## Introduction
This project aims to develop a system that predicts whether a person is likely to develop heart disease within the next 10 years. Every year, it affects hundreds of thousands of people and puts a big strain on healthcare. Python and machine learning techniques were used to build and test several models for this purpose. The goal is to support early identification of high-risk individuals so that preventive measures can be taken before serious health issues occur.

## Dataset
We used a dataset containing medical and personal information from around 4,000 patients. This data was collected as part of a large health study focused on understanding risk factors for heart disease. The dataset includes 4,000 rows and 16 columns, covering details such as age, gender, education, smoking habits, blood pressure, cholesterol, BMI, diabetes status, and glucose levels. Each record also has a final column that tells us whether the person developed heart disease within 10 years. 

## Overview
The process began with data preprocessing and exploratory data analysis (EDA) to clean and understand the dataset. Then, several classification models were developed and optimized using GridSearchCV to improve their performance. Finally, the models were evaluated using metrics like accuracy and ROC AUC to identify the best predictors of heart disease risk.

### EDA
- Missing values were imputed using the median for numerical and mode for categorical features.
- Outliers in systolic blood pressure and glucose were handled using capping and flooring techniques.
- Univariate and bivariate analysis revealed higher blood pressure among smokers and a positive correlation between age and glucose.
- Feature selection removed weak predictors like currentSmoker and diabetes, while key predictors identified were BMI, glucose, blood pressure, and cholesterol.

### Models
- **Decision Tree**- Accuracy improved from 73.7% to 85% after hyperparameter tuning. The model's interpretability made it useful for identifying key decision paths. However, its AUC remained moderate at 0.67, up from 0.5, indicating limited separation between classes despite the tuning.

- **Logistic Regression**- Achieved the highest accuracy of 86.2% and an AUC of 0.73. The model performed well overall and was effective in detecting at-risk individuals, but like other models, it faced challenges with true positive predictions.

- **Support Vector Machine (SVM)**- Reached an accuracy of 85.6% with an AUC of 0.72. The linear SVM provided solid performance, especially after tuning, and handled high-dimensional features well, although it lacked interpretability compared to tree-based models.

- **Random Forest**- Delivered an accuracy of 85.1% and an AUC of 0.69. While slightly lower in performance than Logistic Regression and SVM, it offered better feature importance insights and robustness against overfitting.

- **Voting Classifier (Ensemble)**- Combined predictions from Logistic Regression, SVM, and Random Forest to achieve an accuracy of 85.7% and an AUC of 0.72. This ensemble model balanced the strengths of its components, showing competitive performance with improved generalization.

## Conclusion
This project explored five machine learning models to predict 10-year heart disease risk, with BMI, glucose, blood pressure, and cholesterol identified as key predictors. Logistic Regression and the Voting Classifier showed the best overall performance. However, all models struggled with true positive prediction. Future improvements can include boosting techniques and more diverse health data to enhance accuracy and clinical usefulness.
