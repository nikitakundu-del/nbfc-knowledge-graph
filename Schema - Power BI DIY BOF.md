# Schema - Power BI DIY BOF

Type: semantic schema

Confidence: Trusted for documented model structure.

## Core Semantic Tables

- `BOF_DIY_LEAD_JOURNEY`: hidden helper table at lead grain, carrying journey milestone timestamps.
- `BOF_DIY_STEP_FACT`: dashboard journey fact at lead × configured step grain.
- `BOF_DIY_FRICTION_FACT`: tracked friction/rework event fact.
- `BOF_DIY_FIRST_STEP_FACT`: lead × started-stage fact for first-step selection analysis.
- `APPLICATION_DETAILS`: application/disbursal fact used for outcome measures.
- `Calendar`: shared date dimension for cohort, event, and disbursal analysis.

## Lead-Journey Construction

Confidence: Trusted.

`BOF_DIY_LEAD_JOURNEY` is built at one-row-per-lead grain from `CFSPL_NBFC_DB.GA4_LOANS24.EVENT`. Its cohort, milestone, completion, friction, and elapsed-time rules are documented in [[Analysis - BOF GA Funnel Semantic Model]].

Source traceability: Snowflake worksheet execution `01c64b6e-0002-73d8-0008-3056269004ee`, executed 2026-08-10T10:54:09.482Z; reviewed 2026-08-17.

## Connected Knowledge

- [[Dashboard - DIY BOF]]
- [[Metrics - Power BI Semantic Metrics]]
- [[Analysis - BOF GA Funnel Semantic Model]]
