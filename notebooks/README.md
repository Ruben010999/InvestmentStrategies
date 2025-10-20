# Investment Strategies — Quantitative Research Project

## Overview
This project presents a comprehensive **quantitative research study** comparing multiple portfolio allocation and trading strategies using **Python, SQL, and financial time series analysis**.

The objective is to evaluate how different portfolio construction methods perform under varying market conditions, focusing on:

- **Return consistency**
- **Volatility control**
- **Drawdown resilience**
- **Risk-adjusted performance**

The project is implemented as a **multi-notebook research pipeline**, moving from data ingestion to portfolio construction and final comparative evaluation.

---

## Project Structure

| Notebook | Description |
|-----------|-------------|
| **01_database_ingestion.ipynb** | Builds the local SQLite database and downloads/caches price data for ETFs, stocks, bonds, and commodities. |
| **02_buy_and_hold.ipynb** | Implements a baseline **Equal-Weighted Buy & Hold** strategy as a passive benchmark. |
| **03_momentum.ipynb** | Tests **12-Month Momentum (12M-1)** with and without volatility targeting adjustments. |
| **04_volatility_targeting.ipynb** | Introduces dynamic risk control through **volatility targeting** mechanisms and sensitivity analysis. |
| **05_portfolio_combination.ipynb** | Combines strategies using **Risk Parity** and **Equal-Weight Aggregation**, evaluating performance across time and asset classes. |
| **06_mean_reversion.ipynb** | Explores a **Mean Reversion** approach based on z-score signals and compares it to trend-following models. |
| **07_final_conclusion.ipynb** | Provides the final synthesis, identifying the most balanced and resilient strategies for long-term and short-term investment horizons. |

---

## Data Universe

The study uses a **diversified asset universe** to represent both equity growth and defensive diversification components.

- **ETFs:** `VTI`, `SPY`, `QQQ`, `ARKK`  
- **Stocks:** `AAPL`, `MSFT`, `AMZN`, `GOOGL`, `META`, `TSLA`, `NVDA`  
- **Diversifiers:** `AGG`, `TLT`, `IEF`, `BIL`, `GLD`, `DBC`, `VNQ`, `EFA`, `EEM`, `XLE`, `XLV`  
- **Benchmark:** `^GSPC` (S&P 500)

**Period:** `2015-01-01 – 2025-01-01`  
**Data Source:** Yahoo Finance API (via `yfinance`)

---

## Methodology Highlights

1. **Data Engineering:**  
   - Automated data ingestion and caching using SQLite.  
   - Daily adjusted close prices, merged and cleaned for analysis.

2. **Backtesting Framework:**  
   - Daily rebalancing, transaction cost modeling, and volatility normalization.  
   - Unified functions for portfolio returns, Sharpe ratio, CAGR, volatility, and max drawdown.

3. **Strategies Tested:**  
   - **Equal-Weighted Buy & Hold** — Baseline benchmark.  
   - **12-Month Momentum (12M-1)** — Cross-sectional and time-series momentum variants.  
   - **Volatility Targeting** — Adaptive exposure scaling to maintain stable realized volatility.  
   - **Risk Parity** — Equal risk contribution portfolio combining equities, bonds, and commodities.  
   - **Mean Reversion** — Short-term contrarian strategy based on z-score of price deviations.

4. **Evaluation Metrics:**  
   - Annualized return (CAGR)  
   - Volatility  
   - Sharpe ratio  
   - Maximum drawdown  
   - Sensitivity analysis across volatility targets and estimation windows.

---

## Key Findings

- **Buy & Hold** and **12M-1 Momentum** achieved the highest long-term returns but carried similar volatility and drawdowns (~-30%).  
- **Volatility Targeting** improved risk-adjusted performance, reducing drawdowns by half while maintaining strong CAGR.  
- **Risk Parity** delivered smoother equity curves and lower volatility, particularly when applied to a **diversified universe** of low-correlated assets.  
- **Mean Reversion** underperformed in the predominantly trending 2015-2025 environment, as expected, but remains valuable for range-bound markets.  
- The **most balanced profiles** were achieved by combining **12M-1 Momentum (vol-targeted)** with **Risk Parity**, maintaining ≈ 12 % volatility and limited drawdown (≈ -16 %) while preserving long-term compounding efficiency.

---

## Technologies Used
- **Python**: data analysis and modeling  
- **NumPy / Pandas**: numerical computation and time series processing  
- **Matplotlib / Seaborn**: performance visualization  
- **SQLite / SQLAlchemy**: data storage and retrieval  
- **JupyterLab**: research workflow and documentation environment

---

## Author
**Ruben Kostanyan**  
Independent Quantitative Researcher & Data Analyst  
Project developed as part of a self-directed learning program in **Python-based Quantitative Finance**.

---

## License
This project is released for **educational and research purposes**.  
All market data are sourced from public APIs under fair use.

---
