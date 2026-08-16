# Nifty 50 Multi-Factor Investment Strategy

A Python-based quantitative investment research project that develops and backtests a **Nifty 50 multi-factor stock selection strategy** using **Momentum, Low Volatility, and Value** factors.

The model ranks stocks based on standardized factor scores, combines them into a composite ranking, selects the top 5 stocks, and rebalances the portfolio approximately every 21 trading days. The strategy is evaluated against an equal-weighted Nifty 50 benchmark.

## Project Objective

The objective is to demonstrate the application of quantitative finance concepts to portfolio construction and investment research — from market-data collection and factor construction to backtesting, performance attribution, and risk analysis.

## Strategy Framework

The strategy combines three investment factors:

### 1. Momentum

Measures the trailing **12-month price performance** of each stock.

Stocks with stronger historical momentum receive higher scores.

### 2. Low Volatility

Measures historical price volatility over approximately **3 months (63 trading days)**.

Stocks with lower volatility are preferred.

### 3. Value

Uses the **Price-to-Earnings (P/E) ratio** as a valuation measure.

Stocks with lower P/E ratios are preferred as relatively cheaper companies.

## Composite Score

Each factor is standardized using a **Z-score** so that the different metrics can be compared on a common scale.

The composite strategy score is:

**Composite Score = Momentum Z − Volatility Z − P/E Z**

A higher composite score indicates a more attractive combination of momentum, lower volatility, and valuation.

## Portfolio Construction

* Universe: Nifty 50 constituents
* Portfolio size: Top 5 ranked stocks
* Rebalancing frequency: Approximately every 21 trading days
* Weighting: Equal-weighted among selected stocks
* Transaction cost assumption: 20 basis points
* Benchmark: Equal-weighted Nifty 50 universe

## Backtesting & Analysis

The project evaluates:

* Cumulative strategy performance
* Benchmark performance
* Individual factor performance
* CAGR
* Annualized volatility
* Sharpe Ratio
* Sortino Ratio
* Maximum drawdown
* Factor correlation
* Strategy-to-factor correlation
* Sector exposure of current portfolio selections
* Current top 5 stock signals

## Technologies Used

* **Python**
* **Pandas** — data manipulation and analysis
* **NumPy** — numerical calculations
* **yfinance** — market and company data
* **Matplotlib** — performance visualization
* **Seaborn** — correlation and statistical visualization
* **Google Colab** — research and development environment
* **GitHub** — version control and project documentation

## Project Structure

```text
nifty50-multifactor-investment-strategy/
│
├── Nifty_50_MultiFactor_Strategy.ipynb
│
├── README.md
│
└── .gitignore
```

## Key Research Components

The project includes:

1. Nifty 50 universe definition
2. Historical market-data acquisition
3. Momentum factor construction
4. Low-volatility factor construction
5. Value factor construction
6. Cross-sectional Z-score normalization
7. Multi-factor composite ranking
8. Portfolio construction
9. Periodic rebalancing
10. Transaction-cost modelling
11. Benchmark comparison
12. Factor-level performance attribution
13. Drawdown analysis
14. Risk-adjusted performance analysis
15. Sector exposure analysis
16. Strategy dashboard

## Important Methodological Note

The current implementation uses a **current P/E ratio snapshot** when constructing the historical value factor. This creates a methodological limitation because historical point-in-time P/E data is not used.

A more rigorous future version would use historical point-in-time valuation data to eliminate potential look-ahead bias.

## Disclaimer

This project is intended for **educational and quantitative research purposes only**. Backtested performance does not guarantee future results and should not be interpreted as investment advice.
