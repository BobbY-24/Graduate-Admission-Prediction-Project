Graduate Admission Prediction Project
Overview
This project focuses on predicting the chance of graduate admission for applicants based on their academic and profile features. The dataset used is numerical and includes a target column representing the admission chance (percentage). The aim was to perform Exploratory Data Analysis (EDA), build predictive models, and extract actionable insights about admission chances.

Dataset
The dataset contains the following variables:
GRE Score: Graduate Record Examination score (out of 340)


TOEFL Score: Test of English as a Foreign Language score (out of 120)


University Rating: Rating of the university (1–5)


SOP: Strength of Statement of Purpose (1–5)


LOR: Strength of Letter of Recommendation (1–5)


CGPA: Undergraduate GPA (out of 10)


Research: Binary indicator of research experience (0 = No, 1 = Yes)


Chance of Admit: Target column representing probability of admission (0–1 scale)



Steps Completed
1. Data Cleaning & EDA
Verified no major missing values.


Standardized numerical variables where needed.


Correlation analysis showed CGPA, GRE, and TOEFL as the strongest predictors.


Visualization insights:


Higher CGPA strongly correlates with admission chances.


Research experience increases chances modestly.


GRE and TOEFL scores positively influence admission probability.


2. Baseline Models
We started with simple models to establish performance benchmarks:
Linear Regression → R²: 0.8188, MSE: 0.0037


Polynomial Regression (deg=2) → R²: 0.8265, MSE: 0.0035 (best baseline model)


Ridge & Lasso Regression gave similar performance to Linear Regression.


3. Tree-Based Models
Random Forest → R²: 0.7875


Gradient Boosting → R²: 0.7818


Both models performed slightly worse than linear regression in this case, suggesting the relationship is more linear than complex.


4. Neural Network (MLP)
Initial MLP model underperformed → R²: -0.4056.


After hyperparameter tuning:


Best MLP (activation = tanh, hidden_layer_sizes=(100,), alpha=0.01) → R²: 0.5841


Still inferior to linear models, confirming dataset size and linear nature don’t favor deep learning here.


5. Model Optimization
Random Forest Best Params: {max_depth=5, min_samples_split=5, n_estimators=300} → R²: 0.7855


Gradient Boosting Best Params: {learning_rate=0.05, max_depth=3, n_estimators=100} → R²: 0.7821


Polynomial Regression (deg=3) → Cross-validated R²: 0.5091 (overfitting observed)



Key Insights
Best Model: Polynomial Regression (degree=2) → R² = 0.8265.


Most Important Features:


CGPA: Strongest predictor.


GRE & TOEFL: Significant but secondary.


Research: Helpful but not decisive.


SOP & LOR: Moderate contribution.


Non-linear models (trees, neural nets) did not outperform simple linear/polynomial regression, showing that admission chances are largely a linear function of academic scores.



Next Steps
Collect more diverse features (extracurriculars, essays, recommendation quality text analysis).


Try advanced ensemble methods (Stacking, XGBoost, LightGBM).


Build a web-based prediction tool for applicants.



Conclusion
For this dataset, Polynomial Regression (degree=2) provided the best balance of accuracy and interpretability. Admissions chances are highly influenced by CGPA, GRE, and TOEFL, while research experience and recommendation strength play supporting roles.
This project demonstrates how EDA and multiple ML models can guide us to meaningful insights and robust predictions for graduate admission chances.

