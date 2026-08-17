# Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_F1_ATTEMPTED_BASE

Type: table/view
Schema: [[Schema - CFSPL_CF_C2C_DB.PRE_PROD]]
Confidence: Trusted from F1-to-D reference query

## Purpose

Base user/lead visit rows for the F1-to-D dashboard base.

## Key Fields Seen

- `USER_ID`
- `LEAD_ID`
- `VISIT_TIME`
- `EVENT_NAME`
- `MEDIUM`
- `SOURCE`
- `CAMPAIGN`
- `LEAD_FILL_SOURCE`
- `RN`
- `LEAD_VALID_TILL`
- `visit_date`

## Feeds Metrics

- [[Metric - F1 to D Form 1 Filled Flag]]
- [[Metric - F1 to D Form 2 Filled Flag]]
- [[Metric - F1 to D Form 3 Filled Flag]]
- [[Metric - F1 to D Banking Required Flag]]

## Used By

- [[Evidence - F1 to D ETL Base]]

