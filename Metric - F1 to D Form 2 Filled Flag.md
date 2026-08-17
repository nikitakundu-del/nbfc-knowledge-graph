# Metric - F1 to D Form 2 Filled Flag

Type: metric
Confidence: Trusted
Grain: lead/visit

## Definition

Source-aware Form 2 filled flag in the F1-to-D dashboard base.

## SQL Logic

Same source-aware rule as [[Metric - F1 to D Form 1 Filled Flag]], using `cfd.form_2_filled`.

## Sources

- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_F1_ATTEMPTED_BASE]]
- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_CF_DETAILS]]

## Used By

- [[Evidence - F1 to D ETL Base]]

