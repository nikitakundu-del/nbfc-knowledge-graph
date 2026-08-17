# Table - CAPL_GS_DB.PROD.GS_SALES

Type: table
Schema: [[Schema - CAPL_GS_DB.PROD]]
Confidence: Trusted as source reference; external ownership

## Purpose

GS sales source used for token, booking, city, NRT, and token-date volume checks.

## Key Fields Seen

- `bookingid`
- `token_date_time`
- `hub_city`
- `token_type_with_nrt`
- `nrt_updated_at`
- `nrt_token_cancel_reason`

## Used By

- [[Analysis - Agreement Predictor]]
- [[Analysis - Marketing Campaign Lookalikes]]

## Caution

External to NBFC DWH. Confirm ownership and refresh behavior before making stakeholder-facing definitions.

