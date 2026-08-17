# Analysis - SMS Risk and Feature Stamping

Confidence: Partial.

## Purpose

Analyzes SMS risk bucket creation, SMS sync timing, and feature stamping eligibility around lead and task milestones.

## Source Tables Observed

- `CFSPL_AUTOIQ_DB.PROD.B2C_APPOGRAPHY_PROD_CONSUMER_SMS`
- `CFSPL_CF_D2C_DB.PRE_PROD.PSEUDO_ID_APP_ID_MAPPING_ONE_TIME`
- `CFSPL_CF_D2C_DB.PRE_PROD.READ_SMS_DATA2`
- `CFSPL_CF_D2C_DB.PROD.ACTIVE_LEAD_BANKING_DERIVED_FEATURES2`
- `CFSPL_CF_D2C_DB.PROD.ACTIVE_LEAD_NON_BANKING_DERIVED_FEATURES`
- `CFSPL_CF_D2C_DB.PROD.ACTIVE_LEAD_NON_BANKING_DERIVED_FEATURES2`
- `CFSPL_CF_D2C_DB.PROD.GA_DATA_FOR_SMS2`
- `CFSPL_CF_D2C_DB.PROD.SMS_RISK_BUCKET_DATA2`
- `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS`
- `CFSPL_NBFC_DB.PROD.LEAD_DETAILS`
- `CFSPL_NBFC_DB.PROD.TASK_EXECUTION_TIME_PROD_SAARATHI`
- `CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION_LOG`

## Candidate Flags

- `banking_entry_flag`
- `nonbanking_entry_flag`
- `sms_risk_bucket_flag`
- `within_bound_feature_stamping`
- `eligible_for_feature_stamping_at_lead_creation`
- `eligible_for_feature_stamping_at_f1_fill`
- `eligible_for_feature_stamping_at_f2_fill`
- `eligible_for_feature_stamping_at_asset_attach`

## Review Needed

Do not publish stakeholder-facing definitions until privacy, data access, and exact business interpretation are confirmed.

