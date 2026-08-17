# Base Layer Repository

Compatibility filename: `02_Table_Repository.md`.

This is the canonical base-layer hub for databases, schemas, tables/views, fields, keys, grain, relationships, and source lineage. Objects are listed only when explicitly supported by source evidence.

## Layer Navigation

- Model: [[Lineage - Four Layer Model]]
- This layer: [[Schemas - Index]], [[Tables - Index]]
- Next layer: [[01_Metrics_Index]]
- Consumers: [[04_Dashboard_Repository]], [[03_Analysis_Repository]]

## Table Node Hubs

- [[Tables - Index]]
- [[Schemas - Index]]

## Core NBFC Production Tables

| Table | Observed Use | Linked Artifacts |
|---|---|---|
| `CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS` | Loan/application attributes, credit approval timestamp, disbursal timestamp, HPA status, offer/risk variables. | [[Analysis - Marketing Campaign Query]], [[Analysis - Lead Stage Snapshot]], [[Analysis - Agreement Predictor]] |
| `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS` | Booking, lead mapping, booking time, delivery date, booking cancellation/expiry. | [[Analysis - Marketing Campaign Query]], [[Analysis - Agreement Predictor]], [[Analysis - Lead Stage Snapshot]], [[Analysis - U2FF Query ETL]] |
| `CFSPL_NBFC_DB.PROD.LEAD_DETAILS` | Lead attributes and lead creation context. | [[Analysis - Lead Stage Snapshot]], [[Analysis - SMS Risk and Feature Stamping]] |
| `CFSPL_NBFC_DB.PROD.LEAD_STAGE_TABLE` | Form 1 filled flag and stage-level funnel status. | [[Analysis - Marketing Campaign Query]] |
| `CFSPL_NBFC_DB.PROD.ASSET_DETAILS` | Asset/car details in lead stage snapshot and enrichment work. | [[Analysis - Lead Stage Snapshot]] |
| `CFSPL_NBFC_DB.PROD.TASK_EXECUTION_TIME_PROD_SAARATHI` | Workflow timestamps and funnel task timing. | [[Analysis - Lead Stage Snapshot]], [[Analysis - Task TAT and Queue]] |
| `CFSPL_NBFC_DB.PROD.BANKING_DETAILS_PROD_SAARATHI` | Banking detail enrichment. | [[Analysis - NBFC DWH Enrichment Handoff]] |

## Raw/Operational Source Tables

| Table | Observed Use | Linked Artifacts |
|---|---|---|
| `CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION_LOG` | Task-level event log, FCU check completion, offer approval TODO status, task TAT. | [[Analysis - Agreement Predictor]], [[Analysis - Task TAT and Queue]] |
| `CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB.TASK_EXECUTION` | Task execution source in lead stage snapshot and ad hoc FCU completion checks. | [[Analysis - Lead Stage Snapshot]], [[Analysis - Marketing Campaign Lookalikes]] |
| `CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB.OFFER_DETAILS` | System and agent offer terms, latest offer per lead and appointment. | [[Analysis - Lead Stage Snapshot]] |
| `CFSPL_NBFC_DB.PROD_CUSTOMER_FIN_ASSET_DB.LAPP_ASSET_MAPPING` | Offer-to-appointment link through `OFFER_DETAILS.asset_id = LAPP_ASSET_MAPPING.id`; `reference_id` is appointment id. | [[Analysis - Lead Stage Snapshot]] |
| `CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT.CUSTOMER_CREDIT_VARIABLES` | Customer questionnaire attributes and phone. | [[Analysis - Marketing Campaign Query]] |

## C2C / Marketplace / Dashboard Tables

| Table | Observed Use | Linked Artifacts |
|---|---|---|
| `CFSPL_CF_C2C_DB.PROD.F1_TO_D_DASHBOARD_VW` | Funnel/dashboard source for Form 1 to delivery journey. | [[Analysis - Marketing Campaign Query]], [[Dashboard - User To Form 1 Fill]] |
| `CFSPL_CF_C2C_DB.PROD.U2FORM_FILL` | Tableau U2FF dashboard source. | [[Dashboard - User To Form 1 Fill]] |
| `CFSPL_NBFC_DB.PROD.CF_ENTRY_POINTS_FINAL_DATA` | U2FF entry point source. | [[Analysis - U2FF Query ETL]] |
| `CFSPL_NBFC_DB.PROD.GA_EVENTS_DATA_FOR_UCL_FUNNEL` | GA events used for UCL funnel activity. | [[Analysis - U2FF Query ETL]] |
| `CFSPL_CF_D2C_DB.PROD.PSEUDO_ID_USER_ID_MAPPING_NITIN` | Mapping user pseudo ID to user ID. | [[Analysis - U2FF Query ETL]] |
| `CSPL_MKT_DB.PROD.GA4_FIRST_TOUCH_BUYER_USER_TEST_ABINASH` | First-touch marketing attribution. | [[Analysis - U2FF Query ETL]] |
| `CSPL_MKT_DB.PROD.GA_SESSION_ATTRIBUTION_ABINASH_TEST` | Session attribution fields. | [[Analysis - U2FF Query ETL]] |
| `CSPL_MKT_DB.MKT_BI.BUYER_LAST_TOUCH_FINAL` | Last-touch booking attribution in Tableau workbook. | [[Dashboard - User To Form 1 Fill]] |

## PRE_PROD Views Used As Dependencies

| Table/View | Observed Use | Linked Artifacts |
|---|---|---|
| `CFSPL_CF_C2C_DB.PRE_PROD.AGREEMENT_DETAILS` | Agreement details in lead stage snapshot/enrichment. | [[Analysis - Lead Stage Snapshot]], [[Analysis - NBFC DWH Enrichment Handoff]] |
| `CFSPL_CF_C2C_DB.PRE_PROD.BC2D_COHORT_VIEW_TEST` | Cohort and channel attributes. | [[Analysis - Lead Stage Snapshot]] |
| `CFSPL_CF_C2C_DB.PRE_PROD.LEAD_LEVEL_MOST_RELEVANT_BOOKING_AND_ASSET_VW_TEMP_2` | Appointment and asset linkage. | [[Analysis - Lead Stage Snapshot]] |
| `CFSPL_CF_C2C_DB.PRE_PROD.RBV6_DATA_VW` | Risk bucket / V6 risk features. | [[Analysis - Lead Stage Snapshot]] |
| `CFSPL_CF_C2C_DB.PRE_PROD.TNC_ACCEPTED_BASE` | Consent / terms acceptance. | [[Analysis - Lead Stage Snapshot]] |

## F1-to-D Dashboard Base Staging Tables

These are used by [[Evidence - F1 to D ETL Base]], the reference query behind the F1-to-D dashboard base.

| Table/View | Observed Use |
|---|---|
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_F1_ATTEMPTED_BASE` | Base user/lead visit rows and lead fill source. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_CF_DETAILS` | CFD funnel flags, lead/channel attributes, timestamps, status fields. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_BANKING_REQUIRED` | Banking required flag. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_BANKING_INIT` | Banking initiation details. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_BANKING_ATTEMPT` | Banking attempt details. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_BANKING_DETAILS` | Banking completion/source details. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_DISBURSAL_DATA` | Disbursal flags and actual disbursal time. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_TOKEN_STATS` | Token time, visit/token fields, token status. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_CONSENT_OTP` | Consent OTP fields. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_ASSET_CHARACTERISTICS` | Asset and car characteristics. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_ASSIGNED_AGENT` | Assigned agent attributes. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_SENDBACK` | Sendback details. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_ACTIVE_SENDBACK` | Active sendback details. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_TOTAL_SENDBACK` | Total sendback counts/details. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_CALLING_DETAILS` | Calling attempt/connect metrics. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_RED_CHANNEL_TIME` | Red channel timing. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_POINT_OF_INTERVENTION` | Point-of-intervention timestamps. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_NEW_BANKING_STATS` | New banking stats block. |
| `CFSPL_CF_C2C_DB.PRE_PROD.STG_COHORT_VIEW` | Cohort and channel enrichment. |

## External/Flagged Sources

These are referenced by artifacts but should be documented carefully before stakeholder reuse.

| Source | Reason To Flag |
|---|---|
| `CAPL_GS_DB.PROD.GS_SALES` | External to NBFC DWH; used for token/booking fields. |
| `CSPL_MKT_DB.*` | Marketing attribution source; validate ownership and refresh behavior. |
| `CFSPL_AUTOIQ_DB.*` | SMS risk source; needs privacy/access review before broad sharing. |
