# Table - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION

Type: table
Schema: [[Schema - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB]]
Confidence: Trusted as source reference; metric use partial

## Purpose

Task execution table used in same-day UCC FCU completion checks and lead-stage snapshot dependencies.

## Key Fields Seen

- `application_id`
- `task_id`
- `status`
- `created_at`

## Used By

- [[Analysis - Marketing Campaign Lookalikes]]
- [[Analysis - Lead Stage Snapshot]]
- [[Concept - Task Execution]]

