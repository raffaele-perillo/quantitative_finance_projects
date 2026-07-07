# Quantitative Finance Projects — Raffaele Perillo

MSc Quantitative Finance (Bocconi University) · MSc Economics, Data Analytics and Corporate Finance (École Polytechnique)

Two applied projects in systematic equity strategies and volatility modeling, built in Python.

---

## 1. [Volatility Forecasting on Equity Returns: GARCH-Family Models vs. Gradient Boosting](./Volatility_Forecasting_GARCH_vs_GradientBoosting.ipynb)

An end-to-end conditional variance modeling pipeline: ARMA(2,1) conditional mean → GARCH(1,1) baseline → diagnostic testing (ARCH-LM, correlograms) → EGARCH and Asymmetric Power ARCH alternatives to capture leverage effects → model selection via **out-of-sample unbiasedness/efficiency regressions** (not just in-sample fit) → a Gradient Boosting benchmark trained on realized market variance, excess returns, and short-term rates, tuned via time-series cross-validation.

**Key finding:** the best in-sample model (by HQIC/log-likelihood) is not the one that survives out-of-sample forecast validation — a central lesson in avoiding overfit model selection.

## 2. [Momentum Strategy Backtest on S&P 500 (CRSP Data)](./Momentum_Backtest_SP500.ipynb)

A long-only cross-sectional momentum strategy on S&P 500 constituents (1992–2008), ranking stocks on 12-2 momentum into value-weighted decile portfolios, with robustness checks across rebalancing frequency and transaction cost assumptions (15–30 bps, calibrated on AQR execution data).

**Result:** 13.1% annualized return (Sharpe 0.46) under quarterly rebalancing, outperforming the S&P 500 (7.2%) and the long-short UMD factor (10.1%).

## 3. [Comparative Evaluation of VaR Models: Parametric vs. Hybrid Approach](./VaR_Models_Comparison) (Group Project)

One-week Value-at-Risk on a two-bond fixed-income portfolio, using cash flow clumping to map irregular coupon payments onto a limited set of yield curve nodes. Compares a delta-normal parametric model (EWMA and simple-moving-average variance-covariance estimation) against a hybrid historical-simulation approach (BRW-style exponential weighting, full portfolio revaluation) across four evaluation dates.

**Key finding:** the hybrid approach captures significant negative skewness in portfolio returns that the parametric model's normality assumption misses by construction, producing materially different VaR estimates at the 99% confidence level despite similar variance estimates.

---

### Notes
- Data sources: CRSP (momentum project), Bloomberg equity prices and market-wide realized variance/Fama-French factors (volatility project), zero-coupon bond term structure (VaR project).
- All three are coursework-derived (MSc Finance, Bocconi University) but restructured here with narrative section headers for readability.
