# Graduate Admission Prediction

## Overview
I built this project to predict graduate admission chance from academic and applicant-profile features. It compares several regression models and reports model performance using mean squared error and R-squared. I treat the project as a compact supervised learning exercise on a clean tabular dataset.

## Motivation
I used graduate admission prediction as a useful benchmark for regression modeling and feature interpretation. I use the project to demonstrate exploratory analysis, model comparison, and the importance of evaluating multiple baselines rather than relying on one algorithm.

## Dataset
- **Source:** Public graduate admission prediction dataset used in the notebook.
- **File:** `data/admission_data.csv`
- **Size:** 500 records, based on notebook output.
- **Target variable:** admission chance.
- **Important features:** GRE score, TOEFL score, university rating, SOP, LOR, CGPA, and research experience.
- **Known limitations:** Admission decisions are complex and context-dependent; this dataset is simplified and should not be treated as a real admissions model.

## Methods
- Loaded and inspected admission data.
- Performed exploratory data analysis.
- Trained and compared multiple regression models.
- Evaluated models with MSE and R-squared.

## Results
My notebook reports the following model comparison:

| Model | MSE | R-squared |
| --- | ---: | ---: |
| Linear Regression | 0.003705 | 0.818843 |
| Random Forest | 0.004346 | 0.787504 |
| Gradient Boosting | 0.004462 | 0.781815 |
| Neural Net (MLP) | 0.028744 | -0.405567 |
| Ridge Regression | 0.003722 | 0.817979 |
| Lasso Regression | 0.003807 | 0.813824 |
| Polynomial Regression (degree 2) | 0.003548 | 0.826512 |

## Key Insights
- Polynomial regression performed best in the reported comparison.
- Linear and regularized linear models were competitive.
- The MLP result was poor in this setup, likely due to configuration, data size, or scaling choices.
- The dataset is small enough that validation strategy matters.

## Limitations
- The dataset is simplified and may not represent real admissions decisions.
- I do not use this project to prove causal importance of applicant features.
- Cross-validation and uncertainty estimates should be added.
- Ethical limitations around admissions prediction should be stated clearly.

## Future Improvements
- Add cross-validation.
- Add residual analysis and feature coefficient interpretation.
- Document the dataset source.
- Add an ethics note about admissions modeling.

## How to Run
```bash
git clone https://github.com/BobbY-24/Graduate-Admission-Prediction-Project.git
cd Graduate-Admission-Prediction-Project
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/graduate_admission_prediction.ipynb
```
