# Metric - F1 to D Banking Required Flag

Type: metric
Confidence: Trusted
Grain: lead/visit

## Definition

Banking-required flag in the F1-to-D dashboard base.

## SQL Logic

Uses `BR.banking_required` when `BR.BANKING_REQUIRED = 1` and the same source-aware timing rule as [[Metric - F1 to D Form 1 Filled Flag]] is satisfied.

## Sources

- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_BANKING_REQUIRED]]
- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_F1_ATTEMPTED_BASE]]
- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_CF_DETAILS]]

## Used By

- [[Reference Query - F1 to D ETL Base]]

