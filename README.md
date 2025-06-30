# Uber-Demand-Forecast-in-New-York-City


This project analyzes and forecasts hourly Uber pickup demand in New York City using a combination of statistical models and machine learning techniques. The goal is to improve demand prediction accuracy for better resource allocation, reduced surge pricing, and support for urban mobility planning.

## Project Overview

- **Dataset**: NYC Taxi & Limousine Commission (TLC) data (January–June 2015), enriched with weather variables (temperature, precipitation, wind), gas prices, and temporal features.
- **Forecast Target**: Hourly number of Uber pickups.

## Objectives

- Forecast Uber demand using time series and exogenous variables.
- Compare the performance of multiple statistical and machine learning models.
- Identify patterns in demand through EDA and STL decomposition.
- Evaluate model performance using metrics like RMSE, MAPE, AIC, and R².

## Methodology

1. **Exploratory Data Analysis (EDA)**
   - Decomposition of trend and seasonality via STL.
   - Correlation analysis and feature engineering.
   - Outlier detection and handling.
   - Temporal and exogenous variable exploration (temperature, gas prices, wind).

2. **Models Applied**
   - **Statistical Models**:
     - Time Series Linear Model (TSLM) with daily/weekly seasonality
     - ARIMA and ARIMAX
     - Holt-Winters Exponential Smoothing (additive/multiplicative)
   - **Nonlinear Models**:
     - Generalized Additive Models (GAMs: splines, local regressors, mixed)
   - **Machine Learning**:
     - Gradient Boosting (with different depths and learning rates)

3. **Model Evaluation Metrics**
   - RMSE, MAPE, Adjusted R², AIC, BIC
   - Residual diagnostics (ACF, PACF, Ljung-Box test)

## Results Summary

| Model                      | RMSE    | MAPE (%) | Notes                             |
|---------------------------|---------|-----------|-----------------------------------|
| ARIMA(4,0,2)(2,1,0)[24]   | **394.8** | 10.80     | Best performance overall          |
| Holt-Winters Additive     | 533.1   | 17.42     | Good for constant seasonality     |
| TSLM (Weekly)             | 989.0   | 23.01     | Captures seasonality moderately   |
| GAM (Local Regressors)    | 1889.8  | 63.99     | Overfits, weak on extremes        |
| Gradient Boosting (best)  | ~1700   | ~50–58    | Needs tuning, risk of overfitting |

## Conclusion

- **ARIMA** outperformed all models in accuracy and generalization.
- **Exogenous variables** (temperature, gas prices) improved performance modestly.
- **GAMs and Gradient Boosting** were limited by residual autocorrelation and overfitting.
- Future improvements may include hybrid models, additional predictors (e.g. traffic data), and neural forecasting techniques.

## Authors

- [Karim Eugenio Hamdar](https://www.linkedin.com/in/karim-hamdar-326046327/)
- Davide Christian Mancosu Bustos  
- Mehran Farajinegarestan  
Supervisor: Department of Mathematics, University of Padova

## License

This project is for academic and research purposes only.
