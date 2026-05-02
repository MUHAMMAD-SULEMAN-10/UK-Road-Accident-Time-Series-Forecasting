# UK Road Accident Time Series Forecasting

## Project Overview

This project focuses on forecasting UK road accident casualties using statistical forecasting techniques and deep learning models. The analysis uses the UK Road Accident Dataset (2005–2014) to predict accident casualty trends for 2015 and 2016.

The project combines traditional time series forecasting approaches with modern neural network architectures to compare their performance on a relatively small sequential dataset.

---

# Objectives

The main goals of this project are:

* Analyze historical UK road accident casualty trends
* Forecast accident casualty rates for future years
* Compare statistical models with deep learning approaches
* Evaluate whether LSTM-based architectures can learn from a small time series dataset
* Measure forecasting performance using MAE and MAPE metrics

---

# Models Used

## Statistical Forecasting Models

* SARIMA (Seasonal ARIMA)
* Facebook Prophet

## Deep Learning Models

* LSTM (Long Short-Term Memory)
* GRU (Gated Recurrent Unit)
* Bidirectional LSTM
* Convolutional LSTM

---

# Dataset Information

The dataset contains UK road accident records collected between 2005 and 2014.

### Dataset Features

* 1.5+ million accident records
* Accident severity
* Number of casualties
* Weather conditions
* Road conditions
* Date and time information
* Geographic accident locations

### Important Note

The year 2008 is missing from the dataset, so interpolation techniques were used to estimate the missing time series values.

---

# Technologies & Libraries

## Programming Language

* Python

## Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Plotly
* Statsmodels
* pmdarima
* fbprophet / Prophet
* TensorFlow / Keras
* Scikit-learn

---

# Project Workflow

## 1. Data Loading & Cleaning

* Combined accident datasets from multiple CSV files
* Removed columns with excessive missing values
* Dropped rows with null values
* Converted date columns into datetime format
* Generated monthly aggregated casualty data

### Key Data Cleaning Steps

* Null value handling
* Feature removal for high-missing columns
* Datetime conversion
* Monthly resampling
* Linear interpolation for missing 2008 data

---

# Time Series Analysis

## Seasonal Decomposition

Performed multiplicative decomposition to identify:

* Trend
* Seasonality
* Residual patterns

## Stationarity Testing

Used Augmented Dickey-Fuller (ADF) Test to determine whether differencing was required.

## Autocorrelation Analysis

* ACF plots for MA terms
* PACF plots for AR terms

---

# SARIMA Forecasting

SARIMA models were trained to forecast monthly accident casualty trends.

## Key Steps

* Seasonal decomposition
* Stationarity testing
* Auto ARIMA parameter tuning
* Forecasting future casualty rates
* Confidence interval visualization

## Results

* Forecasted a decline in accident casualty rates
* Achieved strong forecasting performance
* MAPE approximately 5%

### Key Insight

The SARIMA model performed well because the dataset showed clear seasonal and trend patterns.

---

# Facebook Prophet Forecasting

Facebook Prophet was used as an alternative forecasting approach.

## Prophet Configuration

* Yearly seasonality enabled
* Multiplicative seasonality mode
* Trend + seasonality decomposition

## Results

* MAPE approximately 1.8%
* Forecasted decreasing casualty trends
* Produced smoother long-term forecasts

### Key Insight

Prophet outperformed SARIMA in overall forecasting accuracy.

---

# Deep Learning Forecasting

## Models Implemented

### LSTM

Long Short-Term Memory network for sequential forecasting.

### GRU

Gated Recurrent Unit architecture with reduced complexity.

### Bidirectional LSTM

Bi-directional sequence learning using forward and backward context.

### Convolutional LSTM

Spatiotemporal learning architecture adapted for univariate time series forecasting.

---

# Data Preprocessing for Neural Networks

* Standard scaling normalization
* Sequence generation using timesteps
* Train-test split
* Reshaping inputs for ConvLSTM

---

# Deep Learning Results

Although MAE and MAPE values were relatively low, the deep learning models struggled to generalize effectively.

## Main Challenge

The dataset contained only around 120 monthly observations after aggregation, which is very small for deep learning models.

## Observations

* LSTM-based models overfitted easily
* Forecast patterns were unstable
* Statistical models outperformed neural networks

---

# Final Conclusion

## Best Performing Model

Facebook Prophet achieved the best forecasting performance overall.

## Key Findings

* UK accident casualty rates showed a declining trend
* Statistical models performed better on small datasets
* Deep learning models require larger datasets for robust forecasting
* Time series preprocessing and interpolation significantly impacted performance

---

# Forecast Insights

## SARIMA Forecast

* Estimated accident casualty decline over 2 years
* Average yearly reduction in casualties observed

## Prophet Forecast

* Predicted approximately 9% decline in accident rates
* Estimated yearly casualty reduction in future years

---

# Repository Structure

```bash
UK-Road-Accident-TimeSeries-Forecasting/
│
├── data/
│   ├── accidents_2005_to_2007.csv
│   ├── accidents_2009_to_2011.csv
│   ├── accidents_2012_to_2014.csv
│
├── notebooks/
│   └── Project_UK_Road_Accident_Timeseries_Forecasting.ipynb
│
├── images/
│   └── forecasting_results.png
│
├── README.md
└── requirements.txt
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/your-username/UK-Road-Accident-TimeSeries-Forecasting.git
```

## Navigate to Project Folder

```bash
cd UK-Road-Accident-TimeSeries-Forecasting
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Future Improvements

* Add XGBoost and LightGBM forecasting models
* Use larger accident datasets
* Include exogenous variables such as weather and traffic flow
* Hyperparameter optimization using Optuna
* Deploy forecasting dashboard using Streamlit

---

# Key Skills Demonstrated

* Time Series Forecasting
* Statistical Modeling
* Deep Learning
* Data Cleaning
* Feature Engineering
* Forecast Evaluation
* Neural Networks
* Sequential Data Analysis

---

# Author

Muhammad Suleman

---

# References

* UK Department of Transport Dataset
* Statsmodels Documentation
* Facebook Prophet Documentation
* TensorFlow/Keras Documentation
* pmdarima Documentation
