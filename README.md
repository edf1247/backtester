# backtester
backtester in python


## Structure

Stock class:
---- ticker
---- purchase price
---- current price
---- number of shares

Portfolio Class:
---- collection of stocks

Strategy class:
---- stop loss
---- take profit
---- Should be able to allocate stocks to the portfolio based on strategy logic

Engine Class:
---- User specifies range of time to perform the backtest
---- User specifies what stock/strategy to benchmark against
---- Reports:
    - Total return %
    - Total return $ amount
    - APR
    - Sharpe
