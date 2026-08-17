# Metric - F1 to D Banking Success Flag

Type: metric
Confidence: Trusted
Grain: lead/visit

## Definition

Banking-success flag in the F1-to-D dashboard base.

## SQL Logic

Uses `cfd.banking_success` when `cfd.BANKING_SUCCESS = 1` and the source-aware timing rule is satisfied.

## Source

- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_CF_DETAILS]]

## Used By

- [[Evidence - F1 to D ETL Base]]

