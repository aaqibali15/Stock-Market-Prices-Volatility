# Stock-Market-Prices-Volatility
This project aims to forecast stock return volatility by integrating econometric models and machine learning techniques. The initial phases focused on implementing the GARCH family of models (GARCH(1,1), GJR-GARCH, and EGARCH) to capture volatility clustering, persistence, and leverage effects.

Findings from Phase 3

GJR-GARCH emerged as the most effective model, achieving the lowest AIC/BIC values.

It successfully modeled asymmetric volatility, where negative shocks generate stronger volatility than positive shocks.

Diagnostic tests confirmed model adequacy, while forecasting results showed mean-reverting volatility with high accuracy (RMSE ≈ 0.0049, MAE ≈ 0.0037).

Deep Data Leakage Diagnosis

A thorough leakage assessment was conducted to verify the reliability of cross-validation results. Key findings include:

No feature-target correlations above 0.3, ruling out explicit leakage.

The target variable exhibited very high autocorrelation (Lag 1 ≈ 0.97, persisting through 15 lags), explaining why shuffle CV seemed to outperform time-series CV.

Regime shifts in volatility were detected, complicating model generalization.

Minimal feature tests confirmed that the issue stems from structural autocorrelation, not data leakage.

## Conclusion & Next Steps

The study confirms that volatility forecasting is challenging due to persistence, clustering, and regime shifts in financial time series. Tree-based ensemble models and neural networks will be explored in subsequent phases to capture non-linear dependencies and improve predictive power.
