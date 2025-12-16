# Trading-Strategy-Backtester
Rule-based trading strategy backtest using Python (moving averages + RSI)

## Overview
This project implements a rule-based trading strategy and evaluates its historical performance using Python.
The goal was to understand how systematic decision rules affect returns and risk.

## Strategy Logic
The strategy enters the market when:
- Short-term trend is positive (Fast Moving Average > Slow Moving Average)
- Price momentum is not overheated (RSI < 70)

The strategy exits to cash when these conditions are not met.

## Methodology
- Historical daily price data downloaded using yfinance
- Technical indicators: Moving Averages (20, 50), RSI (14)
- Signals shifted by one day to avoid look-ahead bias
- Strategy performance compared against Buy & Hold benchmark

## Results Summary (2020–2025)
- Apple (AAPL): Strategy underperformed Buy & Hold in absolute returns but showed smoother equity growth and reduced drawdowns

## Key Learnings
- Rule-based strategies trade off return for risk control
- Avoiding look-ahead bias is critical in backtesting
- Higher returns do not necessarily imply better risk-adjusted performance

## Tools & Libraries
- Python
- pandas, numpy
- matplotlib
- yfinance
