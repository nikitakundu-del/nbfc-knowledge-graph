# Table - CFSPL_NBFC_DB.PROD_CUSTOMER_FIN_ASSET_DB.LAPP_ASSET_MAPPING

Type: table
Schema: [[Schema - CFSPL_NBFC_DB.PROD_CUSTOMER_FIN_ASSET_DB]]
Confidence: Trusted for offer-to-appointment linkage

## Purpose

Maps offer asset IDs to appointment IDs.

## Trusted Join

> Executable source expression intentionally omitted from the sanitized GitHub mirror.

`LAPP_ASSET_MAPPING.reference_id` is used as `appointment_id`.

## Used By

- [[Analysis - Lead Stage Snapshot]]
- [[Concept - Offer Terms]]

