# Table - CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB.OFFER_DETAILS

Type: table
Schema: [[Schema - CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB]]
Confidence: Trusted for offer-term lineage

## Purpose

Offer-level source for DS and agent/final offer terms.

## Key Fields Seen

- `lead_id`
- `asset_id`
- `offer_type`
- `ltv`
- `roi`
- `tenure`
- `disbursable_loan_amount`
- `total_loan_amount`
- `asset_details:vehicleSellingPrice`
- `emi`
- `updated_at`

## Trusted Logic

Latest offer per lead, appointment, and offer type:

> Executable source expression intentionally omitted from the sanitized GitHub mirror.

## Used By

- [[Analysis - Lead Stage Snapshot]]
- [[Concept - Offer Terms]]

