# Table - CFSPL_CF_C2C_DB.PRE_PROD.STG_CF_DETAILS

Type: table/view
Schema: [[Schema - CFSPL_CF_C2C_DB.PRE_PROD]]
Confidence: Trusted from F1-to-D reference query

## Purpose

Core CFD funnel detail source for F1-to-D flags, channels, status, and timestamps.

## Key Fields Seen

- `lead_channel`
- `ds_channel`
- `FORM_1_FILLED`
- `form_2_filled`
- `form_3_filled`
- `NON_OGL`
- `PRE_APPROVED`
- `BANKING_INITIATED`
- `BANKING_SUCCESS`
- `LOGIN_FLAG`
- `CREDIT_ASSESSED_STATUS`
- `LATEST_FCU_APPROVED_TIMESTAMP`
- `TNC_ACCEPTED_TIMESTAMP`
- `disbursed_time`

## Feeds Metrics

- [[Metric - F1 to D Form 1 Filled Flag]]
- [[Metric - F1 to D Form 2 Filled Flag]]
- [[Metric - F1 to D Form 3 Filled Flag]]
- [[Metric - F1 to D Banking Attempted Flag]]
- [[Metric - F1 to D Banking Success Flag]]
- [[Metric - F1 to D Login Flag]]
- [[Metric - F1 to D Credit Assessed Flag]]
- [[Metric - F1 to D Credit Approved Flag]]
- [[Metric - F1 to D FCU Flag]]
- [[Metric - F1 to D Disbursal Flag]]

## Used By

- [[Evidence - F1 to D ETL Base]]

