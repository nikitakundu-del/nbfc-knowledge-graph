# Metric - F1 to D Form 1 Filled Flag

Type: metric
Confidence: Trusted
Grain: lead/visit

## Definition

Source-aware Form 1 filled flag in the F1-to-D dashboard base.

## SQL Logic

Use `cfd.form_1_filled` when either:

- `cfd.FORM_1_FILLED = 1` and `f1a.LEAD_FILL_SOURCE = 'saarthi'`
- `cfd.FORM_1_FILLED = 1` and `datediff(day, cfd.LEAD_CREATION_DATE, f1a.VISIT_TIME) between -1 and 9999` and `f1a.LEAD_FILL_SOURCE = 'simpler'`

## Sources

- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_F1_ATTEMPTED_BASE]]
- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_CF_DETAILS]]

## Used By

- [[Evidence - F1 to D ETL Base]]
- [[Concept - F1 to D Funnel]]

