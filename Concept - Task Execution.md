# Concept - Task Execution

Type: business concept

## Definition

Task execution data represents workflow/task status movement in the NBFC journey. It is used for FCU completion, task TAT, sendback, pickup, and queue analytics.

## Source Tables

- [[Table - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION_LOG]]
- [[Table - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION]]
- [[Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_TIME_PROD_SAARATHI]]

## Analyses

- [[Analysis - Agreement Predictor]]
- [[Analysis - Task TAT and Queue]]
- [[Analysis - Marketing Campaign Lookalikes]]

## Trusted Logic

- FCU agreement event in [[Analysis - Agreement Predictor]]: `task_id ILIKE '%fcu_check%'` and `status = 'COMPLETED'`.
- Credit approved event in [[Analysis - Agreement Predictor]]: `task_id ILIKE '%initiate%offer%approval%'` and `status = 'TODO'`.

