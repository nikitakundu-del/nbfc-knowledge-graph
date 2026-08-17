# Analysis - Task TAT and Queue

Confidence: Partial.

## Purpose

Analyzes task queue, pickup, hold, and completion timings from task execution logs and lead/application context.

## Source Tables Observed

- `CFSPL_NBFC_DB.PROD.TASK_EXECUTION_TIME_PROD_SAARATHI`
- `CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION_LOG`
- `CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS`
- `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS`
- `CFSPL_NBFC_DB.PROD.LEAD_DETAILS`
- `CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB.OFFER_DETAILS`
- `CFSPL_NBFC_DB.PROD_CUSTOMER_FIN_LEAD_DB.LEAD_AGENT_MAPPING_AUD`
- `CFSPL_NBFC_DB.PROD_PARTNER_FIN_AGENT_DB.AGENT`
- `CFSPL_NBFC_DB.PROD_PARTNER_FIN_AGENT_DB.FOLLOWUP`

## Candidate Metrics

- Queue time
- Pickup time
- Hold time
- Pickup-to-complete time
- Total TAT
- Sendback cycle count
- Hold-to-pickup count

## Review Needed

Confirm stage definitions, sendback treatment, status transitions, and whether timestamps should use first, latest, or paired events.

