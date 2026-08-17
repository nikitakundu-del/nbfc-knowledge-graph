# Analysis - Agreement Predictor

Confidence: Trusted for the listed source tables and derived flags.

## Purpose

Builds a rolling date spine over recent token bookings and evaluates token/activity state, agreement completion, and credit approval events.

## Source Tables

- [[Table - CAPL_GS_DB.PROD.GS_SALES]]
- [[Table - CFSPL_NBFC_DB.PROD.BOOKING_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION_LOG]]

## Temporary Tables

- `date_spine`
- `tel_events`
- `base`
- `rolling`
- `aggregated_data`

## Key Logic

### TEL Event Mapping

- `AGREEMENT`: `task_id ILIKE '%fcu_check%'` and `status = 'COMPLETED'`.
- `CREDIT_APPROVED`: `task_id ILIKE '%initiate%offer%approval%'` and `status = 'TODO'`.

### City Mapping

`hub_city` is bucketed into Delhi - NCR, Chennai, Hyderabad, Bangalore, Ahmedabad, Pune, Mumbai, and Rest of India.

### Token Date Fields

- `booking_id`: `gs.bookingid`
- `lead_id`: `bd.lead_id`
- `application_id`: `bd.lead_id`
- `token_date_time`: `gs.token_date_time`
- `expired_booking_date`: first available of `delivery_date`, `booking_cancel_date`, `booking_expiry_date`

## Trusted Metrics / Flags

- [[01_Metrics_Index#Trusted Metrics|Agreement on Date Flag]]
- [[01_Metrics_Index#Trusted Metrics|Credit Approved on Date Flag]]
- [[01_Metrics_Index#Trusted Metrics|Active Tokens on Date]]

## Links

- [[02_Table_Repository]]
- [[03_Analysis_Repository]]
