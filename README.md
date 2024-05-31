# Pokémon Combat Power Prediction

This project serves as a learning exercise in machine learning and data science. It aims to predict the combat power of Pokémon based on various attributes. The dataset includes several features such as type, health points, attack, defense, and more. The data contains null values and outliers, which are handled through data cleaning processes.


## Dataset Description

The dataset contains the following columns:

- **Name**: Name of the Pokémon.
- **Type 1**: Primary type of the Pokémon (e.g., Grass, Fire, Water, etc.).
- **Type 2**: Secondary type of the Pokémon, if any.
- **Combat Power**: Total combat power of the Pokémon.
- **HP**: Hit Points, indicating the Pokémon's health.
- **Attack**: Attack power of the Pokémon.
- **Defense**: Defensive power of the Pokémon.
- **Sp. Atk**: Special Attack power of the Pokémon.
- **Sp. Def**: Special Defense power of the Pokémon.
- **Speed**: Speed attribute of the Pokémon.
- **Generation**: Generation of the Pokémon.
- **Legendary**: Whether the Pokémon is legendary or not.

## Steps Involved

### 1. Data Cleaning

#### Handle Missing Values
- **Numerical Columns**: Imputed with the median value.
- **Categorical Columns**: Imputed with the most frequent value.

#### Handle Outliers
- Capped at the 1st and 99th percentiles for numerical columns.

### 2. Feature Engineering

- **Encoding Categorical Variables**: One-hot encoding is used for the 'Type 1' and 'Type 2' columns.
- **Encoding 'Legendary' Column**: Converted to integer type.

### 3. Model Building

- **Feature Set and Target Variable**: The feature set includes all columns except 'Name' and 'Combat Power'. The target variable is 'Combat Power'.
- **Train-Test Split**: The data is split into training and test sets with a test size of 20%.

#### Models

1. **Random Forest Regressor**
   - **File**: `randomforest_model.ipynb`
   - **Description**: A Random Forest Regressor used to predict combat power.
   - **Evaluation**: Root Mean Squared Error (RMSE) is approximately 8.06% of the average combat power.

2. **XGBoost Regressor**
   - **File**: `xgboost_model.ipynb`
   - **Description**: An XGBoost Regressor with hyperparameter tuning using GridSearchCV.
   - **Best Parameters**: 
     - `n_estimators`: 200
     - `learning_rate`: 0.1
     - `max_depth`: 5
     - `subsample`: 0.8
     - `colsample_bytree`: 0.8
   - **Evaluation**: RMSE is approximately 5.48% of the average combat power.

3. **Stacked Regressor**
   - **File**: `stacked_model.ipynb`
   - **Description**: A stacking model combining XGBoost, LightGBM, and CatBoost regressors with a Linear Regression as the meta-model.
   - **Evaluation**: RMSE is approximately 3.76% of the average combat power.

## Requirements

- pandas
- numpy
- scikit-learn
- xgboost
- lightgbm
- catboost

## Results

- **Random Forest Regressor**: Prediction error is approximately 8.06% of the average combat power.
- **XGBoost Regressor**: Prediction error is approximately 5.48% of the average combat power.
- **Stacked Regressor**: Prediction error is approximately 3.76% of the average combat power.
