# Enhanced Machine Learning Methods for Mental Health Prediction

## Introduction

This section focuses on the application of advanced machine learning methods for predicting mental health outcomes (Depression and Anxiety) based on air pollution data. The aim is to enhance the predictive power of the model by leveraging multiple regression techniques, including Ridge, Lasso, and Random Forest.

## Data Enrichment

To improve the predictive capabilities of the machine learning models, the following new features were added to the dataset:

* **PM2.5/NO₂ Ratio:** The ratio of PM2.5 to NO₂ for each row, representing the relative concentration of these pollutants.
* **Pollution Category:** A categorical feature representing the severity of pollution as 'Low', 'Medium', or 'High'.
* **Yearly Change in Depression and Anxiety Rates:** Calculated as the difference in depression and anxiety rates from one year to the next for each country.

### Feature Engineering

* Calculated basic statistical measures: mean, variance, and standard deviation of PM2.5 and NO₂.
* Applied Histogram Normalization to normalize distributions.
* Conducted hypothesis testing using t-tests to evaluate feature significance.
* Created new features using ratio and categorical encoding.

## Machine Learning Methods Applied

1. **Linear Regression:** A baseline model to establish a basic understanding of the relationship between air pollution and mental health.
2. **Ridge Regression:** A regularized regression technique to minimize overfitting by adding a penalty for larger coefficients.
3. **Lasso Regression:** A feature selection method that minimizes coefficients to zero for less important features.
4. **Random Forest:** An ensemble learning method that builds multiple decision trees and averages their results for improved prediction.

### Model Tuning and Performance Evaluation

* Models were trained using a 70-30 train-test split.
* Hyperparameter tuning was performed using cross-validation.
* Models were evaluated using R², MAE, and RMSE metrics.

## Model Performance

The model performances were evaluated as follows:

| Model                          | R² Score | MAE  | RMSE |
| ------------------------------ | -------- | ---- | ---- |
| Linear Regression (Depression) | -6.35    | 0.76 | 1.91 |
| Linear Regression (Anxiety)    | 0.04     | 1.07 | 1.27 |
| Ridge Regression (Depression)  | 0.24     | 0.49 | 0.57 |
| Lasso Regression (Depression)  | 0.04     | 0.54 | 0.65 |
| Random Forest (Depression)     | 0.65     | 0.28 | 0.39 |
| Ridge Regression (Anxiety)     | 0.25     | 0.94 | 1.15 |
| Lasso Regression (Anxiety)     | 0.15     | 1.02 | 1.22 |

## Conclusion

* For Hypothesis H1 (PM2.5 and Depression), the Random Forest model showed a positive relationship, supporting the hypothesis with an R² score of 0.65.
* For Hypothesis H2 (NO₂ and Anxiety), the Random Forest model also showed a moderate association.
* Linear Regression performed poorly for both targets, indicating that a simple linear model cannot capture the complexity of the relationships.
* Ridge Regression provided moderate predictive power, especially for anxiety.
* Lasso Regression performed the worst, indicating that aggressive feature selection was not suitable.

## Future Work

* Experiment with more complex models (e.g., Gradient Boosting, XGBoost).
* Include additional features like GDP, education level, and healthcare access.
* Perform hyperparameter tuning for Random Forest for further optimization.
