# Modeling the Stock Market Using Chaos Theory

An independent quantitative finance project exploring whether chaos theory can be used to model and predict stock price movements. The analysis applies mathematical frameworks from nonlinear dynamics — including the Hénon map, Lyapunov exponents, fractal analysis, and Monte Carlo simulation — to real market data for Microsoft (MSFT) and Amazon (AMZN).

---

## Motivation

Stock prices are widely described as chaotic systems — sensitive to initial conditions, nonlinear, and difficult to predict. This project investigates that claim mathematically, building progressively from simple linear regression toward chaos-theoretic and stochastic models to understand where each approach succeeds and breaks down.

---

## Methods

| Method | Purpose |
|---|---|
| Linear Regression | Baseline trend modeling of adjusted close prices |
| Quadratic Regression | Capturing nonlinear price curvature |
| Normal Distribution Modeling | Estimating probability of daily return ranges |
| Hénon Map | Visualizing chaotic attractor behavior using regression parameters as initial conditions |
| Fractal Analysis | Computing fractal dimension to quantify price series complexity |
| Lyapunov Exponents | Measuring sensitivity to initial conditions over 20-day windows |
| Monte Carlo Simulation | Simulating 1,000 future price paths using geometric Brownian motion |

---

## Data

- **Source:** Yahoo Finance
- **Stocks:** Microsoft Corporation (MSFT), Amazon Inc. (AMZN)
- **Period:** February 19, 2022 – February 19, 2023
- **Observations:** 250 trading days
- **Price used:** Adjusted close price

Raw data is available in the `/data` directory as `.csv` files.

---

## Key Findings

- Linear regression achieved R² of **0.8356 (MSFT)** and **0.8829 (AMZN)**, indicating strong fit over the sample period but limited predictive power due to market nonlinearity
- Normal distribution modeling estimated a **90.84% probability** of MSFT daily returns falling between 0–3%, and **84.98%** for AMZN
- Hénon map analysis revealed chaotic attractor behavior consistent with nonlinear price dynamics
- Lyapunov exponents were **negative for both stocks**, indicating local convergence rather than divergence — suggesting the sample period did not exhibit strong chaos despite broader market volatility
- Monte Carlo simulation (1,000 paths, 250 days) using geometric Brownian motion produced plausible price distributions anchored to historical return statistics

---

## Limitations

- 250-day sample window is relatively small; longer historical data would improve model robustness
- Linear and quadratic regression models do not account for market randomness or external shocks
- Fractal analysis alone is insufficient for investment decisions and should be combined with other technical analysis methods
- The Hénon map application uses regression slope parameters as initial conditions, which is a simplification — results should be interpreted as illustrative rather than predictive
- Monte Carlo simulation assumes returns are normally distributed and stationary, which may not hold during periods of structural market change

---

## How to Run

**Requirements:** R (≥ 4.0)  
No additional packages required — base R only.

```r
# Clone the repo, then run either script:
source("code/amazon_monte_carlo.R")
source("code/msft_monte_carlo.R")
```

Each script will:
1. Load the stock price data
2. Run 1,000 Monte Carlo simulations over 250 trading days
3. Plot all simulated price paths with the mean path overlaid in blue

`set.seed(42)` is included in both scripts for reproducibility.

---

## Tools & Languages

- **R** — statistical modeling, Monte Carlo simulation, fractal analysis
- **Microsoft Excel** — regression modeling, descriptive statistics, normal distribution computation
- **Wolfram Alpha** — Hénon map visualization, integral computation
- **Yahoo Finance** — data collection

---

## Author

**Ishaan Gowda**  
The International School Bangalore  
Independent Quantitative Finance Project
