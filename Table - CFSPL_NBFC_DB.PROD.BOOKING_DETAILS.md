# Table - CFSPL_NBFC_DB.PROD.BOOKING_DETAILS

Type: table
Schema: [[Schema - CFSPL_NBFC_DB.PROD]]
Confidence: Trusted from provided SQL

## Purpose

Booking and lead mapping table used for booking, delivery, cancellation, expiry, and token/booking linkage.

## Key Fields Seen

- `booking_id`
- `lead_id`
- `booking_time`
- `delivery_date`
- `booking_cancel_date`
- `booking_expiry_date`

## Feeds Metrics

- [[Metric - Booking Flag]]
- [[Metric - Delivery Flag]]

## Used By

- [[Analysis - Marketing Campaign Query]]
- [[Analysis - Marketing Campaign Lookalikes]]
- [[Analysis - Agreement Predictor]]
- [[Analysis - Lead Stage Snapshot]]
- [[Analysis - U2FF Query ETL]]

