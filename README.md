📈 Tata Motors Stock Price Forecasting using ARIMA & SARIMA
🔹 Overview

This project focuses on forecasting daily closing prices of Tata Motors stock using classical time series models — ARIMA and SARIMA.
The goal was to build a reliable forecasting pipeline by applying proper preprocessing, statistical diagnostics, and model evaluation.

🎯 Objective
Forecast future stock prices using historical data
Compare ARIMA and SARIMA performance
Evaluate accuracy using MAPE (Mean Absolute Percentage Error)
📊 Dataset

The dataset contains historical daily stock prices of Tata Motors with the following columns:

Date
Open
High
Low
Close
Adjusted Close
Volume

👉 The model uses Close price for forecasting.

⚙️ Methodology
1️⃣ Data Preprocessing
Converted Date column to datetime format
Sorted data chronologically
Removed duplicate timestamps
Set Date as index
Ensured continuous daily frequency
Handled missing values using forward fill
2️⃣ Stationarity Check
Used ADF (Augmented Dickey-Fuller test)
Applied first-order differencing to make the series stationary
3️⃣ Parameter Selection
PACF → p (AutoRegressive order)
ACF → q (Moving Average order)
Differencing → d

Final ARIMA parameters:

(p, d, q) = (4, 1, 2)
4️⃣ ARIMA Model
Built baseline ARIMA model
Evaluated residuals
Observed remaining structure → indicated missing seasonal component
5️⃣ Seasonality Detection
Used time series decomposition
Observed repeating patterns
Confirmed need for seasonal modeling
6️⃣ SARIMA Model

Extended ARIMA to include seasonal effects:

SARIMA(p,d,q)(P,D,Q,s) = (4,1,2)(4,1,2,12)
7️⃣ Model Evaluation
Used time-based train-test split
Evaluated using MAPE
📈 Results
Model	Performance
ARIMA	Underperformed
SARIMA	MAPE = 2.86%

👉 SARIMA captured both short-term and seasonal patterns effectively.

📌 Key Insights
Proper preprocessing is critical for time series models
Stationarity is essential for ARIMA-based models
ACF & PACF help in parameter selection
Seasonal patterns significantly improve forecasting accuracy
SARIMA outperformed ARIMA for this dataset
🛠️ Technologies Used
Python
Pandas
NumPy
Matplotlib / Plotly
Statsmodels
Scikit-learn
🚀 How to Run
pip install pandas numpy matplotlib statsmodels scikit-learn

Run the notebook or script:

python main.py
📉 Evaluation Metric

MAPE (Mean Absolute Percentage Error)

Measures average % deviation between predicted and actual values
Achieved: 2.86% (Strong performance)
⚠️ Limitations
Stock prices are inherently volatile and influenced by external factors
Model uses only historical price (no external variables)
Assumes consistent seasonal patterns
🔮 Future Improvements
Incorporate external features (news, macro indicators)
Try advanced models (LSTM, Prophet)
Hyperparameter tuning
Use longer historical data
🎤 Summary

Built a time series forecasting model using ARIMA and SARIMA. After preprocessing and ensuring stationarity, used ACF/PACF for parameter selection. SARIMA captured seasonal patterns and achieved a MAPE of 2.86%, indicating strong predictive performance.