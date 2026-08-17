# Concept - Offer Terms

Type: business concept

## Definition

Offer terms are DS/final financing terms such as ROI, tenure, disbursable loan amount, total loan amount, car selling price, and EMI.

## Trusted Lineage

- DS offered terms: latest `SYSTEM_OFFER`
- Final/agent terms: latest `AGENT_OFFER`
- Appointment link: `OFFER_DETAILS.asset_id = LAPP_ASSET_MAPPING.id`
- Appointment id: `LAPP_ASSET_MAPPING.reference_id`

## Source Tables

- [[Table - CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB.OFFER_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD_CUSTOMER_FIN_ASSET_DB.LAPP_ASSET_MAPPING]]

## Analysis

- [[Analysis - Lead Stage Snapshot]]
