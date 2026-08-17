# Analysis - U2FF Query ETL

Confidence: Trusted for source table mapping; partial for every derived funnel metric until reviewed.

## Purpose

Builds User-to-Form-Fill funnel input by combining entry point behavior, GA activity, booking flags, UCL flags, and marketing mix.

## Temporary Tables

- `first_entry`
- `user_activity`
- `booking_flags`
- `ucl_flags`
- `mkt_mix`

## Source Tables

- `CFSPL_NBFC_DB.PROD.CF_ENTRY_POINTS_FINAL_DATA`
- `CFSPL_NBFC_DB.PROD.GA_EVENTS_DATA_FOR_UCL_FUNNEL`
- `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS`
- `CFSPL_CF_D2C_DB.PROD.PSEUDO_ID_USER_ID_MAPPING_NITIN`
- `CSPL_MKT_DB.PROD.GA4_FIRST_TOUCH_BUYER_USER_TEST_ABINASH`
- `CSPL_MKT_DB.PROD.GA_SESSION_ATTRIBUTION_ABINASH_TEST`

## Candidate Fields Observed

- `entry_point_flag`
- `visit_flag`
- `form_1_initiated`
- `form_1_completed`
- `booking_flag`
- `token_flag`
- `cancellation_flag`
- `returning_bc_user`
- `channel_group_final`
- `session_channel_group_final`
- `session_sub_channel`

## Promotion Rule

Promote any field from this note into [[01_Metrics_Index]] only after confirming:

- grain: user, lead, booking, session, or activity date
- dedupe rule
- date window
- exact numerator and denominator

