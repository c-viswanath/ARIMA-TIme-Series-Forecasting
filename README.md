# ARIMA-Time-Series-Forecasting of Natural Gas Price

This project involves predicting the future prices of natural gas using historical data and ARIMA modeling techniques. The provided code performs data preprocessing, time series analysis, and both manual and automated ARIMA model fitting to generate price predictions for an extended period of time.

### Prerequisites

Ensure that you have the following libraries installed:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `statsmodels`
- `pmdarima`

You can install the required libraries using pip:
```bash
pip install pandas numpy matplotlib seaborn statsmodels pmdarima
```

### Dataset

The dataset `Nat_Gas.csv` should be placed in the `/content` directory. The CSV file should have at least two columns:
- `Dates`: The date of the recorded prices.
- `Prices`: The recorded prices of natural gas.

### Instructions

1. **Load and Preprocess Data:**
    - The dataset is loaded and sorted by dates.
    - A line plot of the prices is generated to visualize the historical data.

2. **Seasonal Trend Analysis:**
    - The plot shows that natural gas prices generally rise at the start of the year and decrease at the end of the year, especially in winter. This trend is used to make future predictions.

3. **Log Transformation:**
    - Log transformation of the price data is performed to stabilize the variance.

4. **Splitting Data:**
    - The data is split into training and testing sets with a ratio of 80:20.

5. **Autocorrelation and Partial Autocorrelation:**
    - ACF and PACF plots are generated for the original and differenced data to help identify the order of the ARIMA model.

6. **ADF Test:**
    - Augmented Dickey-Fuller test is conducted to check the stationarity of the series.

7. **ARIMA Model:**
    - Manual fitting of the ARIMA model with specified order (p, d, q).
    - Residuals of the model are analyzed to ensure they are normally distributed and random.

8. **Forecasting:**
    - Predictions are made for the test data and extended for 24 more periods (2 years).
    - Both manual and auto ARIMA models are used for forecasting.
    - The predicted values are plotted alongside the original data for comparison.

9. **Model Evaluation:**
    - Mean Absolute Error (MAE), Mean Absolute Percentage Error (MAPE), and Root Mean Squared Error (RMSE) are calculated for both manual and auto ARIMA models.

10. **Interactive Prediction:**
    - A function `get_price_for_date(date)` is provided to predict the price for a given date within the specified range.
    - The user can input a date to get the predicted price.

### How to Run

1. Ensure the dataset `Nat_Gas.csv` is in the `/content` directory.
2. Open the notebook and go to `Runtime > Run All`.
3. Follow the prompts to enter a date and get the predicted price for that date.

### Example

```python
date_input = input("Enter a date in between (2020-09-31 and 2026-08-31) in the format (YYYY-MM-DD): ")
result = get_price_for_date(date_input)
print("Price on", date_input, ": $", result)
```

### Output

The script will provide a line plot of the historical and predicted prices and print the predicted price for the user-specified date.

### Conclusion

This project demonstrates time series analysis and forecasting using ARIMA models. Both manual and automated ARIMA fitting are compared, and the model's predictions are evaluated for accuracy using various error metrics.

---

By following the steps in this README, you can successfully run the provided code to predict natural gas prices and analyze the results.
