# Product specification

## Purpose

Give a trader — or a desk — a transparent team of agents that does the repetitive, disciplined part of trading gold: watching the data, reading the regime, looking for setups, weighing the news, enforcing risk, placing and managing orders, and keeping a complete record. Every step is visible, and the system refuses to act when it should not.

## Scope

| Area | Capability |
|---|---|
| Market | XAUUSD (gold vs US dollar) · M15 cycles · H1 and H4 research datasets |
| Agents | 12: data guard, regime, 3 strategy analysts, macro, arbiter, risk, execution, position, audit, research |
| Strategies | Trend pullback · volatility breakout · liquidity sweep / range reversion · macro blackout gate |
| Risk | 12 fixed Guardian rules · emergency stop · position limit of one |
| Execution | Simulated broker (local) · fake-money MetaTrader 5 demo account (cloud) |
| Macro | Live economic calendar + news headlines → clear / high risk / blackout, every 15 minutes |
| Research | Data library with quality checks · backtester with a cost model · walk-forward and stress tests · shadow runner · shadow history |
| Interface | 16 screens: Command Center, Live Agent Floor, Workflow Map, Decision Timeline, Risk Center, Market Overview, Positions & Journal, System Health, Backtesting, Shadow Runner, Live Shadow, Demo Trades, Macro Read, Shadow History, Settings, Data Library |
| Records | Every cycle, event, decision, order and safety action in UTC, exportable |

## Non-goals

- Live-money trading.
- Any claim of profitability, accuracy or protection from loss.
- Letting a model choose risk, position size or deployment.
- Treating a short demo period or a single backtest as proof of an edge.

## Success criteria

- Every cycle is reproducible and fully traceable in the Decision Timeline.
- Every uncertain or failed input resolves to NO TRADE.
- Every risk rejection names the rule that caused it.
- The emergency stop survives restarts and resets.
- Results are reported in R and currency, losses included, from the audit store.

## Status — November 2026

- Platform, risk engine, cloud demo and control room: **complete and running**.
- Strategies: **no winning edge demonstrated** (see [results.md](results.md)).
- Next: research into fundamental and macro inputs, offline first.
