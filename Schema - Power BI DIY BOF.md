# Schema - Power BI DIY BOF

Type: semantic schema

Layer: Base

Confidence: Trusted for documented model structure.

## Core Semantic Tables

- `BOF_DIY_LEAD_JOURNEY`: hidden helper table at lead grain, carrying journey milestone timestamps.
- `BOF_DIY_STEP_FACT`: dashboard journey fact at lead × configured step grain.
- `BOF_DIY_FRICTION_FACT`: tracked friction/rework event fact.
- `BOF_DIY_FIRST_STEP_FACT`: lead × started-stage fact for first-step selection analysis.
- `APPLICATION_DETAILS`: application/disbursal fact used for outcome measures.
- `BOF_DIY_TASK_ACTOR_FACT`: task-execution rows for BOF DIY leads, with task, status, product, channel, funnel, actor, and timestamp attributes.
- `TASK_EXECUTION_LOG`: BOF-scoped task-log rows joined to the lead journey by application identifier.
- `Actor Bucket`: lead-level semantic bridge for the Customer, Saarathi, and Other actor groupings.
- `Calendar`: shared date dimension for cohort, event, and disbursal analysis.

## Lead-Journey Construction

Confidence: Trusted.

`BOF_DIY_LEAD_JOURNEY` is built at one-row-per-lead grain from `CFSPL_NBFC_DB.GA4_LOANS24.EVENT`. Its cohort, milestone, completion, friction, and elapsed-time rules are documented in [[Analysis - BOF GA Funnel Semantic Model]].

Source traceability: Snowflake worksheet execution `01c64b6e-0002-73d8-0008-3056269004ee`, executed 2026-08-10T10:54:09.482Z; reviewed 2026-08-17.

## Connected Knowledge

- Physical sources: [[Table - CFSPL_NBFC_DB.GA4_LOANS24.EVENT]], [[Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG]]
- Metrics: [[Metrics - BOF Task Actor]], [[Metrics - Power BI Semantic Metrics]], [[01_Metrics_Index]]
- Dashboard: [[Dashboard - DIY BOF]]
- Analysis: [[Analysis - BOF GA Funnel Semantic Model]], [[Analysis - BOF Task Actor Model]]

## Task and Actor Relationships

Confidence: Trusted.

- `BOF_DIY_TASK_ACTOR_FACT` is at task-execution-row grain and joins the journey lead through its lead identifier. Its cohort and task-activity dates connect to local date tables; task activity also has an inactive relationship to the shared Calendar for alternate date-context measures.
- `TASK_EXECUTION_LOG` is at source task-log-row grain and joins the journey by application identifier. Its task-activity date has an inactive Calendar relationship.
- `Actor Bucket` is a lead-level bridge related actively and bidirectionally to the journey. A lead may occur in more than one actor bucket because it can have tasks handled in different contexts.

Source traceability: Power BI semantic model `DIY BOF Dashboard`, tables, partitions, relationships, and exact measure definitions read 2026-08-20. Physical lineage resolves to `CFSPL_NBFC_DB.GA4_LOANS24.EVENT` and `CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG`.

Graph model: [[Lineage - Four Layer Model]].
