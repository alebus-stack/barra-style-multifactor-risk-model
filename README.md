# Barra-Style Multi-Factor Portfolio Risk Model

This project implements a **Barra-style equity multi-factor risk model** from scratch using Python, following the methodology used by institutional risk systems.

The model decomposes portfolio risk into **systematic factor risk** and **idiosyncratic risk**, and estimates factor covariances dynamically.

---

## Model Overview

The pipeline follows these steps:

1. **Universe Selection**
   - S&P 500 equities
   - Daily total returns

2. **Factor Construction**
   - Style factors:
     - Value
     - Growth
     - Momentum
     - Volatility
     - Size
     - Quality
     - Leverage
   - Industry factors using sector dummy variables

3. **Cross-Sectional Regression**
   - Daily estimation of factor returns using stock-level exposures

4. **Factor Covariance Estimation**
   - Exponentially Weighted Moving Average (EWMA)

5. **Specific Risk Estimation**
   - Idiosyncratic variance from regression residuals

6. **Portfolio Risk Decomposition**
   - Factor risk contribution
   - Specific risk contribution
   - Total portfolio volatility

---

## Mathematical Framework

For each day:

rᵢ = 𝐗ᵢ · 𝐟 + εᵢ


Where:
rᵢ = return of asset i
𝐗ᵢ = vector of factor exposures for asset i
𝐟 = vector of factor returns
εᵢ = asset-specific (idiosyncratic) return

Portfolio variance:

σₚ² = 𝐰ᵀ · 𝐗 · Σ𝐟 · 𝐗ᵀ · 𝐰 + 𝐰ᵀ · Σε · 𝐰

Where:
σₚ² = total portfolio variance
𝐰 = vector of portfolio weights
𝐗 = matrix of factor exposures
Σ𝐟 = covariance matrix of factor returns
Σε = diagonal matrix of specific variances

---

## Outputs

- Daily factor return time series
- Factor covariance matrix
- Asset-specific risk estimates
- Portfolio risk attribution by factor

---

## Technologies Used

- Python
- pandas, numpy
- statsmodels / scikit-learn
- matplotlib / seaborn

---

## Applications

- Equity portfolio risk management
- Factor exposure monitoring
- Stress testing and scenario analysis
- Foundation for alpha + risk integrated models

---

