# Heart Disease Prediction Capstone Project

## Project Overview

This project focuses on predicting heart disease using machine learning models and is divided into four main parts:

1. **Exploratory Data Analysis**
2. **Logistic Regression**
3. **XGBoost Classification**
4. **Stacked Models**

## The Dataset
The dataset is UCI's Heart Disease data from 6/30/1988. ([Heart Disease Dataset](https://archive.ics.uci.edu/dataset/45/heart+disease))

It is comprised of 303 instances of 13 features that involve patient characteristic such as age, sex, diagnosis, and various objective medical measurements. There is a binary target variable, 1 for heart disease and 0 for the absence of it.

## Project Evolution
The initial goal was to replicate or perhaps outperform the baseline midpoint metrics stated as "Baseline Model Performance" on the dataset website:

|Model Type|Accuracy|Precision|
|-|-|-|
|Logistic Regression|81.579|83.185|
|XGBoost Classification|81.579|83.185|

The Logistic Regression with cross validation came out slightly superior:
- Logistic Regression Test Accuracy: 86.667%
- Logistic Regression Test Precision: 83.333%


XGBoost Classification with grid seach was mixed:
- Best XGBoost Test Accuracy: 83.333%
- Best XGBoost Test Precision: 75.000%

Looking at the feature importances suggested that there may be potential in combining the models somehow.

![Logistic Regression Feature Importance](/notebooks/images/logistic_regression_feature_importance.png)

![XGBoost Classification Feature Importance](/notebooks/images/xgboost_feature_importance.png)


Experimentation was undertaken, but combining the models as peers in a voting manner did not improve results, perhaps because there is enough overlap in feature importance.

However, stacking the models did improve performance:
- Stacked Model Test Accuracy: 88.333%
- Stacked Model Test Precision: 84.000%

## Summary of Findings

Combining two strong machine learning approaches yielded superior results to either one alone and stacking generally leads to more robust or reliable predictions.

Consistently important features like coronary artery disease, thalassemia, and chest pain can be thought of as likely more clinically significant entities.

Modeling like this can be used to inform the design of prospective clinical studies to assess effectiveness.


## Notebooks

1. **[Exploratory Data Analysis](./notebooks/EDA.ipynb)**
2. **[Logistic Regression](./notebooks/logistic_regression.ipynb)**
3. **[XGBoost Classification](./notebooks/xgboost_classification.ipynb)**
4. **[Stacked Models](./notebooks/stacked_models.ipynb)**

## Libraries Used

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost

## Usage Instructions

1. Clone the repository.
2. Navigate to the `notebooks` folder.
3. Open the Jupyter notebooks in order and run the cells to reproduce the analysis and models.

## References
> Janosi,Andras, Steinbrunn,William, Pfisterer,Matthias, and Detrano,Robert. (1988). Heart Disease. UCI Machine Learning Repository. https://doi.org/10.24432/C52P4X.

With gratitude to UCI for making these datasets available.



## Author

Casey Martell, ND, MBA
<br>May 2024