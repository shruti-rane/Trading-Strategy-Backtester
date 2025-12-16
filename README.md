# Trading Strategy Backtester (Python)

## Introduction
This project implements a rule-based trading strategy and evaluates its historical performance using Python.  
The objective is to understand how systematic decision rules affect returns and risk.

The strategy is tested on multiple large-cap US equities:
- Apple (AAPL)
- Microsoft (MSFT)
- Alphabet / Google (GOOGL)

Historical price data is sourced via Yahoo Finance.

---

## Strategy Logic
The strategy follows a simple technical rule set:

The strategy enters the market when:
- Short-term trend is positive (Fast Moving Average > Slow Moving Average)
- Price momentum is not overheated (RSI < 70)

The strategy exits to cash when these conditions are not met.

---

## Methodology
For each stock, the following steps are performed:

1. Historical daily price data downloaded using yfinance
2. Technical indicators:
   - 20-day (fast) and 50-day (slow) Moving Averages
   - 14-day Relative Strength Index (RSI)
3. Signals shifted by one day to avoid look-ahead bias
4. Computed daily returns and strategy returns
5. Applied transaction costs on position changes
6. Strategy performance compared against Buy & Hold benchmark

---

## Performance Metrics
The following metrics were used to evaluate the strategy:

- **Final Equity**: Growth of $1 invested
- **CAGR**: Compound Annual Growth Rate
- **Sharpe Ratio**: Risk-adjusted return
- **Maximum Drawdown**: Worst peak-to-trough loss
- **Number of Trades**: Strategy activity level

---

## Results Summary (2020–2025)
1. Buy & Hold achieved higher absolute returns during strong bull markets
2. The strategy exhibited:
  - Reduced exposure during certain drawdown periods
  - Smoother equity curves
  - Lower volatility compared to Buy & Hold

The strategy prioritizes risk management over maximum profits

---

## Key Learnings
- Rule-based strategies trade off return for risk control
- Avoiding look-ahead bias is critical in backtesting
- Higher returns do not necessarily imply better risk-adjusted performance
- Strategy behavior must be evaluated across multiple assets for robustness

---

## Tools & Libraries
- Python
- pandas
- numpy
- matplotlib
- yfinance
