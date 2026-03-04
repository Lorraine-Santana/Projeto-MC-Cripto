# Bitcoin Price Prediction — Monte Carlo Simulation

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

Probabilistic forecasting model for Bitcoin (BTC-USD) prices using **Monte Carlo simulation**, combined with financial risk metrics **VaR** and **CVaR**.

---

## Overview

This project applies quantitative finance techniques to model and forecast Bitcoin price behavior over a 180-day horizon. Rather than predicting a single price path, the model generates thousands of simulations based on historical return distributions, producing a probability distribution of possible future prices.

---

## Techniques

| Technique | Description |
|---|---|
| **Monte Carlo Simulation** | 2,500 price paths simulated over 180 days |
| **Log Returns** | Normalization of daily returns for statistical modeling |
| **Value at Risk (VaR)** | Maximum daily loss at 95% confidence level |
| **Conditional VaR (CVaR)** | Expected loss in the worst 5% of scenarios |
| **Confidence Intervals** | ±1.96σ bands around the mean forecast path |

---

## Results

| Metric | Value |
|---|---|
| Last BTC price (reference) | $85,235.38 |
| Annualized volatility | 42.68% |
| Daily VaR (95%) | -3.86% |
| Daily CVaR (95%) | -4.98% |
| 5-day cumulative VaR | -8.62% |
| Forecast horizon | 180 days |

---

## Stack

- **Python 3.12**
- **yfinance** — historical market data via Yahoo Finance API
- **pandas** — data manipulation and time-series handling
- **numpy** — numerical computing and random sampling
- **matplotlib** — price charts and simulation visualization
- **seaborn** — return distribution plots
- **scipy** — statistical functions

---

## Project Structure

```
bitcoin-price-prediction/
├── notebooks/
│   └── bitcoin_monte_carlo.ipynb   # Main analysis notebook
├── .gitignore
├── requirements.txt
├── pyproject.toml
└── README.md
```

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Lorraine-Santana/bitcoin-price-prediction.git
cd bitcoin-price-prediction
```

### 2. Install dependencies

Using pip:
```bash
pip install -r requirements.txt
```

Or using Poetry:
```bash
poetry install
```

### 3. Run the notebook

```bash
jupyter notebook notebooks/bitcoin_monte_carlo.ipynb
```

---

## How It Works

1. **Data collection** — Fetches 1 year of BTC-USD OHLCV data from Yahoo Finance
2. **Feature engineering** — Computes daily percentage returns and log returns
3. **Risk metrics** — Calculates VaR and CVaR at the 95% confidence level
4. **Simulation** — Runs 2,500 Monte Carlo paths using bootstrapped log returns
5. **Visualization** — Plots all simulation paths, mean forecast, and 95% confidence bands overlaid on historical prices

---

## Author

**Lorraine Santana** — [@Lorraine-Santana](https://github.com/Lorraine-Santana)
