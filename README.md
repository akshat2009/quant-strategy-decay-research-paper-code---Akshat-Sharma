# quant-strategy-decay-research-paper-code---Akshat-Sharma
Code for my research paper on quantitative strategy decay. Includes full implementations of all three trading strategies, the backtesting framework, and realistic constraints like costs, turnover, and rebalancing. All paper results are reproducible from this repo.

# Quant Strategy Decay — Reproducible Research Code

This repository contains the full codebase used in my research paper:

**“Quant Strategy Decay: Why Statistically Significant Trading Strategies Fail to Deliver Consistent Out-of-Sample Performance Under Realistic Constraints”**  
**Author:** Akshat Sharma (Singapore)  

The paper studies a common failure mode in systematic trading: strategies that look statistically strong in backtests but lose reliability once deployed. This repo focuses on reproducibility and practical realism, not on “best possible” backtest performance.

---

## What’s inside

This repo includes:

- **Three strategy implementations** (as studied in the paper)
- A **shared backtesting engine** so the strategies are tested under the same rules
- **Realistic constraints** and “failure points” baked into evaluation:
  - transaction costs and slippage assumptions
  - turnover and rebalancing frequency
  - capacity proxies (liquidity-aware sizing where applicable)
  - regime sensitivity and stability checks
  - re-optimisation / re-fitting logic (walk-forward style when used)
- A consistent pipeline to produce:
  - equity curves and drawdowns
  - risk-adjusted metrics (Sharpe, Sortino, Calmar)
  - robustness checks (OOS splits, rolling windows, parameter stress tests)

Everything required to reproduce the paper’s results should come from this codebase.

---

## Why this repo exists

Backtests often look strong because they quietly assume ideal conditions. Real markets do not.

Common reasons strategies decay outside a backtest:

- **Friction:** costs, slippage, spread, impact  
- **Overfitting:** too many knobs tuned to one sample of history  
- **Non-stationarity:** regimes shift, correlations rotate, volatility changes  
- **Crowding/capacity:** scaling reduces edge  
- **Implementation gaps:** fills, delays, constraints, and execution mismatch  

This repository is designed to *surface* these failure points directly.
