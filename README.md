# Financial Forecasting in FP&A:
## Traditional Methods versus Machine Learning

This repository contains the empirical workflow supporting a dissertation on
financial forecasting in Financial Planning and Analysis (FP&A).

The study compares traditional forecasting methods and machine-learning models
for forecasting two quarterly financial-statement items:

- Operating Income
- Operating Cash Flow

The purpose is not to assume that machine-learning methods always outperform
traditional approaches. Instead, the study examines whether their potential
value depends on target-variable characteristics, data availability, firm
heterogeneity, sectoral differences, and management-reporting requirements.

## Research questions

1. Do machine-learning models improve the out-of-sample forecasting accuracy of
   Operating Income and Operating Cash Flow relative to traditional methods?

2. How does forecasting performance differ between selected Technology and
   Manufacturing firms?

3. What do the findings imply for the use of data-driven forecasting in FP&A
   and management reporting?

## Data sources

- **SEC Financial Statement Data Sets:** quarterly XBRL-based company financial
  statement data
- **Federal Reserve Economic Data (FRED):** CPI, GDP, unemployment rate, and
  federal funds rate

The study uses quarterly data from 2018 to 2025. The period from 2018 to 2024
is used for model training and validation. Observations from 2025 are retained
for final out-of-sample evaluation.

## Sample

The analysis uses a purposive, availability-constrained sample of ten
U.S.-listed companies.

| Sector | Companies |
|---|---|
| Technology | Apple, Microsoft, NVIDIA, Intel, Adobe |
| Manufacturing | Illinois Tool Works, Cummins, 3M, Fortive, IDEX |

The findings should be interpreted as comparative evidence for the selected
sample rather than as results generalizable to all firms or sectors.

## Forecasting models

### Traditional approaches

- Lag-1 naïve baseline
- Four-quarter moving average
- Multivariate linear regression

### Machine-learning approaches

- Random Forest Regressor
- XGBoost Regressor

## Features and evaluation

The final models use lagged company-level financial variables, lagged
macroeconomic indicators, quarterly seasonality controls, and a sector dummy.

Macroeconomic variables include:

- Inflation rate
- GDP growth
- Unemployment rate
- Federal funds rate

All macroeconomic variables are lagged by one quarter to reduce the risk of
contemporaneous information entering the forecast.

Model performance is evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R-squared (R²)
- Forecast Bias
- Mean Absolute Scaled Error (MASE)

Hyperparameters for Random Forest and XGBoost are selected using
expanding-window validation within the 2018–2024 training period. The 2025
data are reserved for final out-of-sample testing.

## Repository structure

```text
notebooks/     Reproducible analysis notebooks
docs/          Methodology, data documentation, and limitations
data/          Data documentation; raw source files are not stored in Git
outputs/       Reproducible result tables and figures
```

## Important limitations

- The study uses a small, purposive sample of ten companies.
- Usable observations vary by target because of missing data and
  target-specific transformation requirements.
- Operating Cash Flow may be reported cumulatively and must be transformed into
  discrete quarterly values.
- SEC XBRL tags can vary across firms and periods.
- The final 2025 test sample is limited, particularly for Operating Cash Flow.
- The period-lagged design reduces information leakage but does not reconstruct
  a fully real-time, filing-date-aligned data vintage.

## Project status

This repository is under active development. The current version provides the
initial analytical workflow. Further updates will include modular notebooks,
exported result tables, figures, robustness checks, and expanded
documentation.
