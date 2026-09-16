# Hyperspectral Data Analysis for Vomitoxin (DON) Prediction

## Overview
This project analyzes a hyperspectral dataset containing spectral reflectance data (446 bands) from corn samples to predict the concentration of vomitoxin (DON), a mycotoxin, measured in ppb. The workflow includes data preprocessing, dimensionality reduction using PCA, and predictive modeling using a Random Forest Regressor with hyperparameter tuning via GridSearchCV.

## Installation
```bash
git clone https://github.com/SimranChawla-27/ML-Intern-Task.git
cd ML-Intern-Task
pip install pandas numpy seaborn matplotlib scikit-learn
```

## Usage
Open `ML_Intern_Simran.ipynb` in Jupyter Notebook or Google Colab and run the cells sequentially to reproduce the preprocessing, PCA, model training, and evaluation steps.

## Repository Structure

## Methodology
- **Preprocessing:** Handled missing values and standardized 446 spectral reflectance features
- **Dimensionality Reduction:** Applied PCA — the top 2 principal components explained ~93% of total variance (87% + 5.8%), indicating strong redundancy across adjacent spectral bands
- **Modeling:** Trained a Random Forest Regressor with hyperparameters tuned via GridSearchCV (n_estimators, max_depth, min_samples_split) using 5-fold cross-validation

## Results
| Metric | Value |
|--------|-------|
| R² | 0.52 |
| MAE | 3940.9 |
| RMSE | 11591.5 |

The model explains approximately 52% of the variance in vomitoxin concentration. The notably higher RMSE relative to MAE suggests the target variable is right-skewed, with a small number of high-toxin outlier samples disproportionately affecting error — a pattern worth further investigation (e.g., outlier-robust modeling or log-transforming the target).

## Key Findings
- Spectral reflectance data shows meaningful predictive signal for vomitoxin concentration, though moderate model accuracy suggests room for improvement (e.g., feature selection, alternate models, or outlier handling)
- High variance explained by just 2 principal components indicates significant redundancy across the 446 spectral bands — fewer, well-chosen bands may perform nearly as well

## Note
This was completed as part of a hands-on ML internship task at Bharti Airtel.
