# Backtest-engine


## DataHandler

~~1. Date distance must be above 60.~~ \
~~2. Check date format~~ \
~~3. If random ticker, pick one on your own.~~ \
~~4. Function - Data = DataHandler(start = "01-01-2024", end = "2024-01-02") - Data.data~~ \

## Strategy

## Account/PM
1. Account, value, inventory, orders
2. maintains positions, cash, margin, realized P&L
3. applies fills, books trades, marks-to-market
4. enforces constraints
5. Portfolio checks risk/limits → passes orders to Broker

## Slippage/transaction

DataHandler emits MarketEvent(t)

Strategy consumes it → emits OrderEvent(t)

Portfolio checks risk/limits → passes orders to Broker

Broker uses execution model → emits FillEvent(t + latency)

Portfolio applies fills, updates positions/cash

End-of-bar/day: mark-to-market + record snapshot
