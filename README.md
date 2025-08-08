# Bitcoin Funding Rate vs. Return Analysis
This repository contains a comprehensive time-series analysis of the relationship between Bitcoin funding rates and its short-term returns, using data collected from Binance and other exchanges.

# Objective
To investigate whether extreme values or directional shifts in the funding rate can provide meaningful signals for forecasting Bitcoin price returns in the short to medium term.

# Dataset
Funding Rate: Hourly funding rate data for BTC/USDT futures on Binance (and optionally other exchanges).
Returns: Hourly and daily price returns of BTC/USDT.
Time Range: Last 6 months (with sampling aligned to funding intervals).

# Analysis Steps


# Correlation Analysis
Compute the Pearson correlation between hourly funding rate and hourly BTC return.
Result: Overall correlation is near zero, suggesting no consistent linear relationship.

# Lagged Correlation
Explore if current funding rates predict BTC returns in the next 1 to 24 hours.
Finding: Lagged correlations remain weak and oscillating, offering little standalone predictive power.

# Rolling Correlation
Compute rolling 24-hour correlations between funding rate and return.
Observation: Correlation varies significantly over time, sometimes turning strongly positive or negative.

# Granger Causality Test
Check whether past funding rates Granger-cause BTC returns (lags 1–6 hours).
Finding: Mixed results; in some intervals, certain lags show statistically significant causal signals.

# Event-Based Return Analysis
Identify extreme funding events using quantile thresholds (top 15%, bottom 10%).
Analyze BTC performance in the following 3, 6, 12, 24, and 48 hours.

Result:
High funding often precedes negative returns (potential long squeeze).
Low funding tends to precede positive returns (short panic followed by rebound).
High Correlation Periods
Isolate windows where funding and return are highly correlated.

# Tools & Technologies

Python (Pandas, NumPy, Matplotlib, Seaborn, Statsmodels)
Jupyter Notebook
Data Format: CSV & Pickle (PKL)

├── data/
│   ├── funding_rate_binance_btc.pkl     # Cleaned funding rate for BTC on Binance
│   ├── btc_returns.csv                  # BTC hourly and daily return data
├── funding-vs-btc-returns.ipynb         # Main analysis notebook
├── README.md                            # Project documentation


# Key Insight
Funding rate can be a valuable sentiment indicator, especially when extreme, but by itself it is not a reliable standalone predictor of price direction. Incorporating it into multi-factor models or as part of event-based signals can improve interpretability and short-term strategy design.

Evaluate BTC's momentum in those periods using forward returns.

Insight: Positive correlation often aligns with trend continuation over the next 24–48 hours.
