# Heart Disease Prediction Model

## Overview
This project develops a machine learning classifier to predict the presence of heart disease in patients using clinical and medical data. Many different models are trained and the final soft voting classifier utilizes all these optimized models to achieve a predictive accuracy of 88.41 %.

## Project Objective
To build a predictive model that accurately identifies patients at risk of heart disease based on medical features including age, blood pressure, cholesterol levels, exercise-induced angina, and other clinical indicators.

## Dataset
- **Source**: [Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)
- **Size**: 918 patient records
- **Features**: 12 clinical attributes
- **Target Variable**: Heart disease presence (binary classification: 0 = No, 1 = Yes)
- **Class Distribution**: 55.3% positive cases, 44.7% negative cases

### Key Features
| Feature | Description | Data Type |
|---------|-------------|-----------|
| Age | Patient age in years | Numeric |
| Sex | Patient sex (M/F) | Categorical |
| ChestPainType | Type of chest pain experienced | Categorical |
| RestingBP | Resting blood pressure (mmHg) | Numeric |
| Cholesterol | Serum cholesterol level (mg/dl) | Numeric |
| FastingBS | Fasting blood sugar > 120 mg/dl | Binary |
| RestingECG | Resting electrocardiogram result | Categorical |
| MaxHR | Maximum heart rate achieved | Numeric |
| ExerciseAngina | Exercise-induced angina (Y/N) | Binary |
| Oldpeak | ST depression induced by exercise | Numeric |
| ST_Slope | Slope of ST segment | Categorical |
| HeartDisease | Target variable (0/1) | Binary |

## Data Processing Pipeline

### 1. Data Cleaning
- **Missing Values**: Identified and handled missing values in RestingBP and Cholesterol columns
- **Imputation Strategy**: Applied median imputation stratified by heart disease status to preserve feature distributions
- **Data Quality**: Removed 1 sample with RestingBP = 0 and 172 samples with Cholesterol = 0

### 2. Exploratory Data Analysis (EDA)
- Analyzed distribution of numerical and categorical variables
- Generated correlation heatmap to identify feature relationships
- Performed countplots for categorical features to understand patient demographics
- Identified male-female distribution ratio (3.75:1)

### 3. Feature Engineering
- **Categorical Encoding**: Applied one-hot encoding to categorical variables:
  - Sex (M/F)
  - ChestPainType (ASY, ATA, NAP, TA)
  - RestingECG (Normal, ST, LVH)
  - ExerciseAngina (N/Y)
  - ST_Slope (Up, Flat, Down)
- **Feature Scaling**: Applied MinMaxScaler normalization to numerical features
- **Final Feature Count**: 16 features (7 numerical + 9 encoded categorical)

### 4. Train-Test-Validation Split
- **Strategy**: Stratified split on gender (SexM) feature to maintain distribution
- **Split Ratio**: 85% training, 15% validation
- **Random State**: Controlled randomization for reproducibility

## Installation & Dependencies

bash
# Install required packages
pip install pandas numpy scikit-learn matplotlib seaborn

# Required versions (tested on):
- Python >= 3.8
- pandas >= 1.3.0
- numpy >= 1.21.0
- scikit-learn >= 0.24.0

## Author
Aniket Bhatia
