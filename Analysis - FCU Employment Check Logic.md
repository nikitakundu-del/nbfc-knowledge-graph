# FCU Employment Check Logic

Confidence: Trusted.

Layer: Analysis

## Purpose

Produces one latest employment-check record per loan and FCU employment-check name, then classifies API-response and review outcomes.

## Source Tables And Join

- `CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION` (`tel`): FCU task context; filtered to completed `fcu_checks` tasks.
- `CFSPL_NBFC_DB.PROD_MONGO_RISK_DB.AUDIT_DETAILS` (`ad`): risk audit trail; joined on trimmed `tel.application_id = ad.loan_id`.
- `CFSPL_NBFC_DB.PROD_CARS24_FIN_CUSTOMER_FIN_CUSTOMER_DB.CUSTOMER_FIELD_SOURCE`: company-name source changes; joined to the normalized loan id and normalized source name.

## Extraction And Grain

- The audit trail is flattened through `audit_trail`, `details:checkTypeDetails`, and `checkResponseDtos`.
- Filters retain `employmentAndIncomeValidation`, audit version `V3`, and `EMPLOYMENT_CHECK` rows.
- Final base grain is one row per trimmed loan id, audit page name, and check name; the latest `updatedAt` is retained with `ROW_NUMBER()`.

## Reusable Logic

- Normalizes the employment-verification source, including `UDHYAM` to `UDYAM`.
- Standardizes source-specific employer response fields for EPFO, GST, and UDYAM into common name, address, and match-score fields.
- `api_responded_flag` requires all three standardized source response components: employer name, employer address, and match score.
- `manual_review_flag` is a pending decision not verified by `AUTO-VERIFIED`; `auto_approved_flag` is an accepted decision verified by `AUTO-VERIFIED`.
- Categories are evaluated in this precedence: additional-info employer update, API response with mismatch/manual review, missing/incomplete API response with manual review, API response with exact score and auto approval, then other.

## Source Traceability

- Snowflake worksheet query ID: `01c65148-0002-7741-0008-305626e76992`
- Executed: 2026-08-11T11:52:33Z

## Four-Layer Lineage

- Base: [[Schema - Power BI FCU Checks Automations]], `CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION`, `CFSPL_NBFC_DB.PROD_MONGO_RISK_DB.AUDIT_DETAILS`, and `CFSPL_NBFC_DB.PROD_CARS24_FIN_CUSTOMER_FIN_CUSTOMER_DB.CUSTOMER_FIELD_SOURCE`
- Metrics: [[Metrics - Power BI Semantic Metrics]], [[01_Metrics_Index]]
- Dashboard: [[Dashboard - FCU Checks Automations]]
- Analysis: this note

Graph model: [[Lineage - Four Layer Model]].
