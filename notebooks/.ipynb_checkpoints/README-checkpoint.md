# Investment Strategies — Quantitative Research Project

## Overview
This project presents a comprehensive quantitative analysis of several investment strategies using Python, SQL, and financial time series data.  
The objective is to evaluate how different portfolio allocation methods perform across various market conditions, focusing on **return consistency, volatility control, and drawdown resilience**.

The project is structured as a multi-notebook research pipeline, progressing from data ingestion to portfolio construction and final comparative evaluation.

---

## Project Structure
| Notebook | Description |
|-----------|--------------|
| **01_database_ingestion.ipynb** | Builds the local SQLite database, downloads/caches price data for ETFs, stocks, bonds, and commodities. |
| **02_buy_and_hold.ipynb** | Implements a baseline **Equal-Weighted Buy & Hold** strategy. |
| **03_momentum.ipynb** | Tests **12-Month Momentum** (12M-1) with and without volatility targeting. |
| **04_volatility_targeting.ipynb** | Introduces dynamic risk control through **volatility targeting** mechanisms. |
| **05_portfolio_combination.ipynb** | Combines strategies using **Risk Parity** and **Equal-Weight Aggregation**, evaluates performance across time windows. |

---

## Data Universe
The universe includes diversified asset classes to capture both equity growth and defensive characteristics:

- **ETFs:** `VTI`, `SPY`, `QQQ`, `ARKK`
- **Stocks:** `AAPL`, `MSFT`, `AMZN`, `GOOGL`, `META`, `NVDA`
- **Diversifiers:** `AGG`, `TLT`, `IEF`, `BIL`, `GLD`, `DBC`, `VNQ`, `EFA`, `EEM`, `XLE`, `XLV`
- **Benchmark:** `^GSPC` (S&P 500)

Period: **2015-01-01 → 2025-01-01**

---

## Methodology
Each notebook builds upon a consistent framework:
1. **Data ingestion and cleaning** from Yahoo Finance into a normalized SQL database.  
2. **Return computation** and **portfolio weighting** via Pandas and NumPy.  
3. **Performance metrics:**  
   - CAGR (Compound Annual Growth Rate)  
   - Annualized Volatility  
   - Sharpe Ratio (risk-adjusted return)  
   - Max Drawdown  

All strategies include transaction costs and rebalancing frequency control.

---

## Results Summary
| Strategy | Sharpe | CAGR (%) | Volatility (%) | Max Drawdown (%) | Key Feature |
|-----------|--------|-----------|----------------|------------------|--------------|
| **Buy & Hold (EW)** | 0.97 | 12.1 | 12.7 | −22.7 | Stable baseline |
| **Momentum 12M-1** | 0.85 | 11.4 | 13.8 | −22.9 | Trend-following bias |
| **Mean Reversion** | 0.28 | 3.2 | 15.9 | −37.2 | Weak in trending markets |
| **Risk Parity** | 0.98 | 15.0 | 15.4 | −22.7 | Most balanced risk allocation |

---

## Key Insights
- **Volatility targeting** enhances stability and Sharpe ratio without major loss of CAGR.  
- **Risk Parity** performs best in multi-asset universes with low correlation — acting as a volatility smoother.  
- **Momentum** thrives during trending markets (e.g., 2017–2021).  
- **Mean Reversion** underperforms in long bull markets but may complement other strategies in mean-reverting environments.  
- **Equal-Weight aggregation** across strategies further stabilizes results.

---

## Conclusion
This research demonstrates a practical framework for quantitative portfolio construction and evaluation.  
It highlights that the **most resilient portfolios are not the highest-return ones**, but those maintaining **balanced exposure, controlled volatility, and crisis resilience**.  
The project establishes a foundation for future extensions, such as **machine-learning-based allocation models** or **macro-regime adaptive strategies**.

---

## Technologies Used
- Python (Pandas, NumPy, Matplotlib)
- SQLite + SQLAlchemy
- Jupyter Notebook
- Yahoo Finance API

---

## Author
Developed by **Ruben Kostanyan** — Physics graduate and aspiring Data Scientist focusing on AI-driven quantitative finance.

