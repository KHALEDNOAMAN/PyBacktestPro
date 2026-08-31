# PyBacktestPro - Strategy Guide

## Built-in Strategies

### Moving Average Crossover
```python
class MACrossover(Strategy):
    fast_period = 10
    slow_period = 50
    
    def next(self):
        if crossover(self.fast_ma, self.slow_ma):
            self.buy()
        elif crossover(self.slow_ma, self.fast_ma):
            self.sell()
```

### RSI Mean Reversion
```python
class RSIStrategy(Strategy):
    rsi_period = 14
    oversold = 30
    overbought = 70
```

## Metrics Explained
| Metric | Good | Excellent |
|--------|------|-----------|
| Sharpe Ratio | > 1.0 | > 2.0 |
| Max Drawdown | < 20% | < 10% |
| Win Rate | > 50% | > 60% |
| Profit Factor | > 1.5 | > 2.0 |
| Calmar Ratio | > 1.0 | > 3.0 |

## Running a Backtest
```bash
python backtest.py \
  --strategy ma_crossover \
  --symbol AAPL \
  --start 2023-01-01 \
  --end 2024-01-01 \
  --capital 10000
```

## Custom Strategy Template
```python
class MyStrategy(Strategy):
    def init(self):
        # Define indicators
        pass
    
    def next(self):
        # Trading logic
        pass
```
