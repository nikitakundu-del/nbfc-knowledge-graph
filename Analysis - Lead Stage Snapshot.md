# Analysis - Lead Stage Snapshot

Confidence: Trusted for offer-term lineage and daily active lead-stage snapshot framing.

## Purpose

Creates one row per `(lead_id, stage)` where the stage was crossed on `current_date - 1` and the lead is currently active. The row carries lead attributes and offer terms.

## Key Filter

- `dts = current_date - 1`
- `lead_status = 'ACTIVE'`

## Offer-Term Lineage

The query sources DS and final offer terms from the latest offers instead of relying on application or booking fields.

### Source Tables

- [[Table - CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB.OFFER_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD_CUSTOMER_FIN_ASSET_DB.LAPP_ASSET_MAPPING]]

### Join Rule

- `OFFER_DETAILS.asset_id = LAPP_ASSET_MAPPING.id`
- `LAPP_ASSET_MAPPING.reference_id` is used as `appointment_id`

### Offer Types

- DS terms: latest `SYSTEM_OFFER`
- Final terms: latest `AGENT_OFFER`

### Latest Offer Rule

`ROW_NUMBER() OVER (PARTITION BY lead_id, appointment_id, offer_type ORDER BY updated_at DESC) = 1`

## DS Fields

- `ds_roi`
- `ds_tenure`
- `ds_disbursable_loan_amount`
- `ds_total_loan_amount`
- `ds_car_selling_price`
- `ds_emi`

## Final / Agent Fields

- `agent_roi`
- `agent_tenure`
- `agent_disbursable_loan_amount`
- `agent_total_loan_amount`
- `agent_car_selling_price`
- `agent_emi`

## Additional Sources

- [[Table - CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD.ASSET_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD.BOOKING_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD.LEAD_DETAILS]]
- [[Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_TIME_PROD_SAARATHI]]
- [[Table - CFSPL_CF_C2C_DB.PRE_PROD.AGREEMENT_DETAILS]]
- `CFSPL_CF_C2C_DB.PRE_PROD.BC2D_COHORT_VIEW_TEST`
- `CFSPL_CF_C2C_DB.PRE_PROD.LEAD_LEVEL_MOST_RELEVANT_BOOKING_AND_ASSET_VW_TEMP_2`
- `CFSPL_CF_C2C_DB.PRE_PROD.RBV6_DATA_VW`
- `CFSPL_CF_C2C_DB.PRE_PROD.TNC_ACCEPTED_BASE`
