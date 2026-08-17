# Table - CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT.CUSTOMER_CREDIT_VARIABLES

Type: table
Schema: [[Schema - CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT]]
Confidence: Trusted from provided SQL

## Purpose

Customer credit variables and questionnaire JSON used for lookalike/customer feature extracts.

## Key Fields Seen

- `_id`
- `lead_details:phone`
- `QUESTIONNAIRE:"date_of_birth"`
- `questionnaire:employment_type`
- `questionnaire:gender`
- `questionnaire:house_type`
- `questionnaire:income`
- `questionnaire:income_proof`
- `questionnaire:marital_Status`
- `questionnaire:pincode_current`

## Used By

- [[Analysis - Marketing Campaign Query]]
- [[Analysis - Marketing Campaign Lookalikes]]
- [[Concept - Marketing Lookalike Audience]]

## Caution

Contains customer-level attributes. Validate access and sharing rules before exposing extracts.

