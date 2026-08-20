# BOF Task and Actor Metrics

Type: metric hub

Layer: Metrics

Confidence: Trusted.

## Canonical Metrics

- [[Metric - BOF Task Execution Rows]]
- [[Metric - BOF Task Execution Leads]]
- [[Metric - BOF Completed Task Execution Rows]]
- [[Metric - BOF Task Actor Bucket Lead Share]]
- [[Metric - BOF Task Log Rows]]
- [[Metric - BOF Task Log Application IDs]]
- [[Metric - BOF Completed Task Log Rows]]

Supporting distinct actor/applicant counts remain model measures but are not promoted as reusable business metrics because their intended reporting semantics are not explicit enough.

## Lineage

[[Table - CFSPL_NBFC_DB.GA4_LOANS24.EVENT]] and [[Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG]] → [[Schema - Power BI DIY BOF]] → this metric family → [[Dashboard - DIY BOF]] → [[Analysis - BOF Task Actor Model]].

Source traceability: exact Power BI measure definitions and relationships from `DIY BOF Dashboard`, read 2026-08-20.
