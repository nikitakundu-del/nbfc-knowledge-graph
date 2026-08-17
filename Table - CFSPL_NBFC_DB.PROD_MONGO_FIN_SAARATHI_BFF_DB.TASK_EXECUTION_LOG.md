# Table - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION_LOG

Type: table
Schema: [[Schema - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB]]
Confidence: Trusted from provided SQL

## Purpose

Task event log used to infer FCU/agreement events, credit approval task state, and task TAT.

## Key Fields Seen

- `application_id`
- `task_id`
- `status`
- `updated_at`
- `created_at`

## Trusted Event Logic

- Agreement event: `task_id ILIKE '%fcu_check%'` and `status = 'COMPLETED'`.
- Credit approval event in agreement predictor: `task_id ILIKE '%initiate%offer%approval%'` and `status = 'TODO'`.

## Used By

- [[Analysis - Agreement Predictor]]
- [[Analysis - Task TAT and Queue]]
- [[Concept - Task Execution]]

