# Table - CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS

Type: table
Schema: [[Schema - CFSPL_NBFC_DB.PROD]]
Confidence: Trusted from provided SQL

## Purpose

Loan/application-level attributes and timestamps used for credit, disbursal, HPA partner, and lead-channel filters.

## Key Fields Seen

- `loan_id`
- `lead_id`
- `lead_channel`
- `first_credit_approved_timestamp`
- `disbursed_time`
- `hpa_status`

## Feeds Metrics

- [[Metric - Credit Approval Flag]]
- [[Metric - Disbursal Flag]]

## Used By

- [[Analysis - Marketing Campaign Query]]
- [[Analysis - Marketing Campaign Lookalikes]]
- [[Analysis - Lead Stage Snapshot]]

