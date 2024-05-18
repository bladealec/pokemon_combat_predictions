# Pokémon Combat Power Prediction

This project aims to predict the combat power of Pokémon based on various attributes. The dataset includes several features such as type, health points, attack, defense, and more. The data contains null values and outliers, which are handled through data cleaning processes.

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
- **Regression Model**: A Random Forest Regressor is used for predicting combat power.
- **Model Evaluation**: The model's performance is evaluated using Root Mean Squared Error (RMSE).

## Requirements

- pandas
- numpy
- scikit-learn

## Results

- Prediction error is approximately 8.06% of the average combat power.

