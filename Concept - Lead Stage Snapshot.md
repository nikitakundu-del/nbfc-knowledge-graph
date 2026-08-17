# Concept - Lead Stage Snapshot

Type: business concept

## Definition

Daily lead-stage snapshot captures active leads that crossed a stage on the prior day and attaches lead, channel, asset, risk, and offer-term attributes.

## Analysis

- [[Analysis - Lead Stage Snapshot]]

## Important Sources

- [[Table - CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD.LEAD_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD.BOOKING_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD.ASSET_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB.OFFER_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD_CUSTOMER_FIN_ASSET_DB.LAPP_ASSET_MAPPING]]

## Key Rule

Offer terms should come from latest `SYSTEM_OFFER` and `AGENT_OFFER` records linked to appointment through `OFFER_DETAILS.asset_id = LAPP_ASSET_MAPPING.id`.

