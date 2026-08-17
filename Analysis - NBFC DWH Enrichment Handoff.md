# Analysis - NBFC DWH Enrichment Handoff

Confidence: Partial as stakeholder metric source; trusted as project/process context.

## Purpose

Documents a prior NBFC DWH enrichment project and the validation workflow used to safely add columns to DWH tables.

## DWH Tables Mentioned

- `CFSPL_NBFC_DB.PROD.LEAD_DETAILS_PROD_SAARATHI`
- `CFSPL_NBFC_DB.PROD.TASK_EXECUTION_TIME_PROD_SAARATHI`
- `CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS_PROD_SAARATHI`
- `CFSPL_NBFC_DB.PROD.ASSET_DETAILS_PROD_SAARATHI`
- `CFSPL_NBFC_DB.PROD.BANKING_DETAILS_PROD_SAARATHI`
- `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS_PROD_SAARATHI`

## Validation Methodology To Reuse

1. Redundancy check against `INFORMATION_SCHEMA.COLUMNS`.
2. Compile and build staged temp tables.
3. Grain/fan-out check with row count and distinct key count.
4. Row parity using overlay diff against current PROD.
5. Fill-rate sanity checks for new columns.

## Important Caution

The handoff states that validation was read-only against production using `SELECT`, `DESCRIBE`, and session temporary tables. Avoid publishing derived columns from this handoff until their final SQL, source table, grain, and validation evidence are attached.

