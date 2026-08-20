# Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG

Layer: Base

Confidence: Trusted.

## Grain and Scope

One source task-log row per task execution. In the BOF semantic model, rows are limited to non-deleted records, task activity from 2026-06-01 onward, and applications or entities connected to the BOF proxy-event cohort.

## Trusted Fields and Relationships

- `entity_identifier` joins task rows to the GA event lead identifier.
- Application identifier, with entity identifier as the fallback used by the model, joins BOF task rows to the lead journey.
- Task status supports the completed-row metrics.
- Task activity timestamp supplies the inactive Calendar date context.
- Actor attributes support the Customer, Saarathi, and Other semantic buckets. No literal employee identifiers are stored here.

This physical object is distinct from [[Table - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION_LOG]].

## Consumers

- [[Schema - Power BI DIY BOF]]
- [[Metrics - BOF Task Actor]]
- [[Analysis - BOF Task Actor Model]]

Source traceability: Power BI semantic model `DIY BOF Dashboard` partition lineage read 2026-08-20.
