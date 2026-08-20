# Metric - BOF Task Actor Bucket Lead Share

Layer: Metrics

Confidence: Trusted.

## Definition

Numerator: distinct task leads in the current actor-bucket context.

Denominator: distinct task leads after removing actor-bucket and actor-bucket-order filters while retaining other report filters.

The Customer, Saarathi, and Other buckets are semantic classifications supported by task actor/channel markers. A lead may have tasks in multiple buckets, so bucket shares are non-exclusive and need not sum to 100%.

Base: [[Schema - Power BI DIY BOF]], [[Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG]]

Dashboard: [[Dashboard - DIY BOF]]

Analysis: [[Analysis - BOF Task Actor Model]]

Source traceability: exact Power BI measure and calculated-table definitions from `DIY BOF Dashboard`, read 2026-08-20. Literal employee identifiers are intentionally omitted.
