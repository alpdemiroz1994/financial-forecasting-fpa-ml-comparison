# Methodology Summary

## Research design

This study uses a quantitative, comparative, and out-of-sample forecasting
design. Traditional forecasting approaches and machine-learning models are
estimated separately for Operating Income and Operating Cash Flow.

## Financial data

Firm-level financial data are obtained from the SEC Financial Statement Data
Sets. The analysis uses quarterly `sub.txt` and `num.txt` files. Numerical
financial facts are linked to filing-level information using the accession
number (`adsh`).

The raw SEC data are filtered for the selected companies using Central Index
Keys (CIKs) and for the financial-statement tags relevant to the analysis.

## Sample

The analysis includes ten selected U.S.-listed firms:

- Technology: Apple, Microsoft, NVIDIA, Intel, and Adobe
- Manufacturing: Illinois Tool Works, Cummins, 3M, Fortive, and IDEX

The sample is purposive and constrained by the availability of usable
quarterly financial observations.

## Target variables

Operating Income is obtained from the `OperatingIncomeLoss` XBRL tag.

Operating Cash Flow is obtained from
`NetCashProvidedByUsedInOperatingActivities`. Because this item may be
reported cumulatively within a fiscal year, discrete quarterly values are
constructed by subtracting the prior cumulative observation within the same
fiscal year.

## Macroeconomic variables

CPI, GDP, unemployment, and the federal funds rate are retrieved from FRED.
The source series are converted to quarterly frequency. CPI inflation and GDP
growth are calculated using four-quarter percentage changes. All
macroeconomic variables are lagged by one quarter before they are merged with
the firm-quarter dataset.

## Forecasting models

The following models are compared:

- Lag-1 naïve baseline
- Four-quarter moving average
- Linear regression
- Random Forest Regressor
- XGBoost Regressor

Random Forest and XGBoost hyperparameters are selected through
expanding-window validation using only the training period.

## Evaluation design

The study applies a chronological split:

- Training and validation period: 2018–2024
- Final out-of-sample test period: 2025

The final test period is not used for feature selection, hyperparameter
selection, or final model fitting. Forecast accuracy is evaluated using MAE,
RMSE, R-squared, Bias, and MASE.
