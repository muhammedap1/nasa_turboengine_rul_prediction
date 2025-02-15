# NASA Turbofan Engine RUL Prediction

## Project Overview

This project aims to predict the **Remaining Useful Life (RUL)** of engines using the **NASA Turbofan Engine Degradation Simulation Dataset**. Predicting RUL is crucial for predictive maintenance, helping to prevent unexpected engine failures by scheduling maintenance at the right time. This project includes **data preprocessing**, **exploratory data analysis (EDA)**, and the creation of several regression models to estimate the RUL of engines.

## Dataset

The dataset used is the **NASA Turbofan Engine Degradation Simulation Dataset**, which consists of sensor readings and operational data for several engines running until failure. Each engine has several operational cycles, and the goal is to predict how many cycles remain before an engine fails based on its sensor data.

- **Train Data**: Contains sensor readings and operational data for each engine run until failure.
- **Test Data**: Contains sensor data for engines where the failure point is unknown.
- **RUL Data**: Contains the actual Remaining Useful Life for the engines in the test data.

## Project Workflow

### 1. Data Preprocessing

- **Feature Engineering**: 
  - Created the `RUL` feature for the training dataset by calculating the difference between the maximum number of cycles and the current cycle for each engine.
  - Extracted useful sensor readings and operational features for model training.

- **Outlier Detection and Handling**: 
  - Conducted outlier analysis on the sensor data to identify and potentially remove any anomalous readings.

- **Scaling**: 
  - Applied **StandardScalar** to normalize the sensor data to ensure features are on the same scale for model training.

### 2. Exploratory Data Analysis (EDA)

- **Important Features**: 
  - Analyzed the most significant sensor readings contributing to the engine's degradation using statistical and correlation analysis.
  - Visualized trends in sensor data over the engine's life cycle.
  
- **Outlier Detection**: 
  - Used visualization techniques to identify potential outliers in sensor data.

- **Correlation Analysis**: 
  - Examined correlations between different sensors and the target (RUL) to identify which sensors have the highest predictive power.

### 3. Model Building

The following regression models were trained and evaluated to predict the RUL of the engines:

- **Lasso Regression** (`Lasso`)
- **Linear Regression** (`LinearRegression`)
- **Support Vector Regression** (`SVR`)
- **K-Neighbors Regressor** (`KNeighborsRegressor`)
- **Random Forest Regressor** (`RandomForestRegressor`)
- **Gradient Boosting Regressor** (`GradientBoostingRegressor`)
- **XGBoost Regressor** (`XGBRegressor`)

Each model was evaluated using appropriate performance metrics, including:
- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**
- **R-squared (R²)**

### 4. Model Selection

After training multiple models, performance comparison was made to select the best model based on the evaluation metrics. The best model was then used for predicting the Remaining Useful Life of the engines in the test set.

## Results

The models were compared based on their ability to predict RUL accurately, and the following conclusions were drawn:

- The **best performing model** was [Support Vector Regression	,Random Forest Regressor], achieving an RMSE of [70.349267	,50.589184] and an MAE of [59.672935	,38.949140].


## Tools and Libraries

The project was implemented using the following tools and libraries:

- **Python** for data preprocessing, modeling, and analysis.
- **Pandas** for data manipulation.
- **Matplotlib** and **Seaborn** for visualization.
- **Scikit-learn** for machine learning models.
- **XGBoost** for the XGBoost regressor.
- **NumPy** for numerical operations.

## How to Run the Project

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/nasa-turbofan-rul-prediction.git
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook or Python script for data preprocessing and model building.

## Future Work

- **Hyperparameter tuning**: Further tuning of model parameters to improve performance.
- **Deep learning models**: Experiment with Recurrent Neural Networks (RNN) or Long Short-Term Memory (LSTM) models for time series prediction.
- **Ensemble models**: Combine multiple models to create an ensemble for potentially better predictions.

## Acknowledgments

- NASA for providing the Turbofan Engine Degradation Simulation Dataset.
- The data science and machine learning community for resources and tutorials.
