# Limitations

## Sample scope

The study uses a small, purposive sample of ten U.S.-listed companies. It is
designed as a comparative empirical analysis and does not aim to provide
statistically representative conclusions for all U.S. firms, industries, or
FP&A environments.

## Data availability

Usable observations differ across companies and target variables. Financial
statement data can contain missing items, reporting differences, and changes
in XBRL tags over time. Results are conditional on the available
firm-quarter observations.

## Operating Cash Flow construction

Operating Cash Flow is often reported as a cumulative year-to-date value.
Quarterly values are derived from differences between cumulative disclosures.
The availability of valid prior-period observations reduces the usable sample
for this target variable.

## Small out-of-sample sample

The 2025 test sample is limited after target-specific data, lag, moving
average, and feature-availability requirements are applied. Operating Cash
Flow has fewer usable test observations than Operating Income. Results should
therefore be interpreted cautiously and as exploratory comparative evidence.

## Scale effects

Companies in the sample differ substantially in size. Dollar-denominated MAE
and RMSE can be disproportionately affected by large firms. MASE and
firm-level results are therefore important complements to pooled error
metrics.

## Information availability

The design uses lagged financial and macroeconomic variables to reduce
information leakage. However, it does not reconstruct a fully real-time data
vintage in which every variable is aligned precisely to its public filing or
release date.

## Model scope

The analysis compares selected traditional methods, linear regression, Random
Forest, and XGBoost. It does not test every possible forecasting approach.
Results should be interpreted as evidence for these specified models and
settings.
