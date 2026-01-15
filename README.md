# Backtest-engine


## DataHandler

~~1. Date distance must be above 60.~~ \
~~2. Check date format~~ \
~~3. If random ticker, pick one on your own.~~ \
~~4. Function - Data = DataHandler(start = "01-01-2024", end = "2024-01-02") - Data.data~~ \

## Strategy

## Account/PM

## Slippage/transaction

DataHandler emits MarketEvent(t)

Strategy consumes it → emits OrderEvent(t)

Portfolio checks risk/limits → passes orders to Broker

Broker uses execution model → emits FillEvent(t + latency)

Portfolio applies fills, updates positions/cash

End-of-bar/day: mark-to-market + record snapshot
