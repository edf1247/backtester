# backtester
A minimal Python backtester with example strategies.

This repository contains a small backtesting framework implemented in
`src/main.ipynb`. The notebook demonstrates downloading price data,
computing indicators, defining strategies, and plotting equity curves.

Features
- Download historical price data with `yfinance`.
- Compute indicators (moving average, RSI) using `pandas` and `pandas_ta`.
- Backtest framework with `Backtest`, `Strategy` base class and examples:
    - `BuyHold`: buy-and-hold equity curve from daily returns.
    - `RSICrossOver`: signals on RSI crossing thresholds (buy on cross above 30, exit on cross below 70).
- Simple performance metrics: total return and drawdown; equity curve plotting with `matplotlib`.

Quick start
1. Create and activate a virtual environment and install dependencies:

     pip install -r requirements.txt

2. Open the notebook and run cells in order: [src/main.ipynb](src/main.ipynb).

Notebook overview
- Inputs: `stocks = ["AAPL", "SPY"]`, date range, and interval.
- `Backtest` class: downloads data, stores multi-index DataFrame, manages strategies, and plots results.
- Strategies derive from `Strategy` and implement `_run()` to populate per-strategy columns:
    - `BuyHold` computes daily returns and cumulative balance from an initial capital.
    - `RSICrossOver` computes RSI signals, assigns trade ids, applies returns only while in market, and computes balance.
- After adding strategies (e.g., `BuyHold`, `RSICrossOver`) call `bt.run()` to execute and print metrics, then view equity curves and `bt.data`.

Dependencies
- Python 3.8+
- yfinance, pandas, numpy, matplotlib, pandas_ta

See [src/main.ipynb](src/main.ipynb) for the full code and runnable examples.
