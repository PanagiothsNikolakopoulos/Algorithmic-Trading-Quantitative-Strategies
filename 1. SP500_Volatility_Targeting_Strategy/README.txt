# Quantitative Analysis of the S&P 500: From Forecasting to a Risk-Managed Strategy

### Project Overview

This project provides a comprehensive, end-to-end workflow for the quantitative analysis of the S&P 500 index. The primary goal was to move beyond simple price forecasting and develop a robust, dynamic trading strategy based on volatility modeling. The entire analysis is conducted in Python, leveraging key data science and financial modeling libraries.

---

### Key Concepts & Methodologies

This project covers several core concepts in quantitative finance:

-   **Time Series Analysis:** Initial analysis of the S&P 500 price data, including stationarity testing (Augmented Dickey-Fuller test) and achieving stationarity through differencing.
-   **ARIMA Modeling:** Building and training an ARIMA model for price forecasting. The project demonstrates both a standard out-of-sample forecast and a more robust **rolling forecast** evaluation to highlight the model's strengths and limitations.
-   **Volatility Modeling (GARCH):** Using a GARCH(1,1) model to capture the time-varying volatility and "volatility clustering" inherent in financial markets. This shifts the focus from predicting price *direction* to forecasting market *risk*.
-   **Quantitative Strategy Backtesting:** Implementing a **Volatility Targeting** strategy that uses the GARCH forecasts to dynamically adjust its market exposure, aiming to maintain a constant level of portfolio risk.
-   **Sensitivity Analysis:** Testing the strategy with different volatility targets (15% vs. 20%) to understand how parameter tuning affects performance and to find an optimal risk profile for the given historical period.

---

### Project Workflow & Pipeline

1.  **Data Sourcing & EDA:** S&P 500 daily data from 2015-2025 was sourced using the `yfinance` library. Initial exploratory analysis included visualizing price trends and plotting 50-day and 200-day moving averages to identify trends and classic trading signals.

2.  **ARIMA Forecasting:** A statistically significant `ARIMA(5, 1, 5)` model was trained. The evaluation clearly showed that while ARIMA is useful for short-term, one-step-ahead predictions (as demonstrated by the rolling forecast), it is unsuitable for long-term forecasting.

3.  **GARCH Volatility Modeling:** A `GARCH(1,1)` model was successfully fitted to the daily returns. The model effectively captured periods of high market stress, most notably the COVID-19 crash in 2020.

4.  **Strategy Implementation & Backtesting:** The GARCH forecasts were used to power a Volatility Targeting strategy. The backtest compared its performance against a passive "Buy and Hold" benchmark.

5.  **Sensitivity Analysis & Optimization:** The strategy was tested with both a 15% and a 20% annualized volatility target.

---

### Key Findings & Conclusion

The main takeaway from this project is the demonstrable superiority of an active risk management approach.

-   The **Volatility Targeting strategy with a 20% target** not only provided significant downside protection during market crashes but also **outperformed the passive Buy and Hold benchmark** in both absolute and risk-adjusted terms (as measured by the Sharpe Ratio) for the 2015-2025 period.
-   The analysis proves that by modeling and forecasting volatility, we can create dynamic strategies that lead to more robust and efficient investment outcomes.

---

### Technologies Used

-   **Language:** Python
-   **Libraries:** Pandas, NumPy, Matplotlib, `yfinance` for data, `statsmodels` for ARIMA, `ARCH` for GARCH, `scikit-learn` for metrics.