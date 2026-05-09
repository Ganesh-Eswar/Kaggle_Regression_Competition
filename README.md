# House Price Prediction using Machine Learning

## Overview

Kaggle competition link: https://www.kaggle.com/competitions/mlp-term-3-2025-kaggle-assignment-1

Explanation video link: https://drive.google.com/file/d/1t00wBhyx7cdZ_ARK8HtHyio2EstkMfRi/view?usp=sharing

This project was developed as part of a Kaggle regression competition focused on predicting house prices using structured housing data.

The objective was to build and compare multiple machine learning models capable of accurately estimating house prices based on features such as location, area type, square footage, number of bathrooms, balconies, and house size.

The project includes:

* Data preprocessing
* Feature engineering
* Outlier removal
* Exploratory Data Analysis (EDA)
* Model training and evaluation
* Hyperparameter tuning
* Ensemble learning

---

# Dataset Description

The dataset contains housing-related information and corresponding property prices.

## Files

* `train.csv` → Training dataset containing features and target variable (`price`)
* `test.csv` → Test dataset where the target variable is hidden
* `sample_submission.csv` → Example submission file for Kaggle

---

# Features Used

| Feature        | Description                       |
| -------------- | --------------------------------- |
| `id`           | Unique identifier                 |
| `area_type`    | Type/category of residential area |
| `availability` | Availability status of property   |
| `location`     | Geographical location of property |
| `size`         | Number of bedrooms/halls/kitchens |
| `total_sqft`   | Total area in square feet         |
| `bath`         | Number of bathrooms               |
| `balcony`      | Number of balconies               |
| `price`        | Target variable (house price)     |

---

# Project Workflow

## 1. Data Loading

Datasets were loaded using Pandas from Kaggle input directories.

---

# 2. Data Preprocessing

Several preprocessing techniques were applied to improve model performance.

## Categorical Encoding

### Area Type Encoding

Used `OrdinalEncoder` to convert:

* `type_I`
* `type_II`
* `type_III`
* `type_IV`

into ordinal numerical representations.

---

### Availability Encoding

Availability values were grouped into:

* Ready to move → `1`
* Future availability → `0`

---

### Location Feature Engineering

* Cleaned inconsistent location names
* Handled missing values
* Grouped rare locations into `"Other"`
* Applied target-based encoding using average location price

---

### Size Encoding

Extracted numerical room counts from textual values such as:

* `2 BHK`
* `3 Bedroom`

and converted them into numerical format.

---

# 3. Data Cleaning

## Duplicate Removal

Duplicate rows were identified and removed.

## Missing Value Handling

Used:

* `SimpleImputer(strategy="median")`

for numerical feature imputation.

---

# 4. Outlier Detection and Removal

Outliers were identified using:

* IQR (Interquartile Range) method
* Boxplot visualization

Features cleaned:

* `location`
* `size`
* `total_sqft`
* `bath`

---

# 5. Feature Scaling

Applied:

* `StandardScaler`

through Scikit-learn Pipelines for standardized feature scaling.

---

# 6. Exploratory Data Analysis (EDA)

Visualizations included:

* Histograms
* Correlation heatmaps
* Bar plots
* Box plots

Libraries used:

* Matplotlib
* Seaborn

---

# Machine Learning Models Used

The project explored multiple regression models for performance comparison.

## Models Implemented

### Linear Models

* Simple Linear Regression
* Ridge Regression
* ElasticNet Regression
* Polynomial Regression

### Neural Networks

* MLP Regressor
* Hyperparameter Tuned MLP

### Tree-Based Models

* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost Regressor

### Kernel Methods

* Support Vector Regressor (SVR)

### Ensemble Models

* Voting Regressor
* Hybrid ensemble models combining:

  * Ridge
  * ElasticNet
  * MLP
  * Random Forest
  * Gradient Boosting

---

# Hyperparameter Tuning

Used:

* `GridSearchCV`
* Cross-validation

for:

* MLP Regressor
* ElasticNet
* Polynomial Regression degree optimization

---

# Evaluation Metric

Model performance was primarily evaluated using:

* R² Score

Additional metrics imported:

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)

---

# Final Outputs

Submission files for different models were generated in CSV format and stored inside outputs folder.

---

# Technologies Used

## Programming Language

* Python

## Libraries

* NumPy
* Pandas
* Scikit-learn
* XGBoost
* Matplotlib
* Seaborn

## Environment

* Kaggle Notebook Environment

---

# Project Structure

```text
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── sample_submission.csv
├── notebooks/
├── outputs/
│   ├── ensemble_regressor.csv
│   ├── nn_mlp_regressor.csv
│   ├── model_comparison.png
│   └── ...
├── README.md
└── requirements.txt
└── Kaggle_Regression_workflow.mp4
```

---

# Key Learning Outcomes

Through this project:

* Multiple regression algorithms were explored
* Feature engineering techniques were applied
* Ensemble learning concepts were implemented
* Hyperparameter tuning and cross-validation were practiced
* Real-world tabular ML workflow was developed

---

# Future Improvements

Potential improvements include:

* Advanced feature selection
* CatBoost / LightGBM integration
* Stacking ensembles
* Better cross-validation strategies
* Automated ML pipelines
* Deep learning regression architectures

---

# Author

Developed as part of a Kaggle Machine Learning Competition focused on house price prediction using regression and ensemble learning techniques.
