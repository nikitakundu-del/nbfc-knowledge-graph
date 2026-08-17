# Metrics Index

Only metrics with explicit logic are included here.

## Metric Node Hubs

- [[Metrics - Funnel Outcomes]]
- [[Metrics - F1 to D Base Flags]]
- [[Metrics - Tableau Dashboard Rates]]

## Trusted Metrics

| Metric | Definition | Grain | Primary Source | Artifact |
|---|---|---:|---|---|
| Entry Point Clicked on User Base GA | `COUNTD(if ENTRY_POINT_FLAG = 1 then LEAD_ID end) / COUNTD(LEAD_ID)` | lead | `ENTRY_POINT_FLAG`, `LEAD_ID` | [[Dashboard - User To Form 1 Fill]] |
| Entry Point Clicked on BC Base GA | `COUNTD(if BOOKING_FLAG = 1 and ENTRY_POINT_FLAG = 1 then USER_ID end) / COUNTD(if BOOKING_FLAG = 1 then USER_ID end)` | user | `BOOKING_FLAG`, `ENTRY_POINT_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| F1 Initiated on Entry Point Clicked GA | `COUNTD(if BOOKING_FLAG = 1 and ENTRY_POINT_FLAG = 1 and FORM_1_INITIATED = 1 then LEAD_ID end) / COUNTD(if BOOKING_FLAG = 1 and ENTRY_POINT_FLAG = 1 then LEAD_ID end)` | lead | `BOOKING_FLAG`, `ENTRY_POINT_FLAG`, `FORM_1_INITIATED`, `LEAD_ID` | [[Dashboard - User To Form 1 Fill]] |
| F1 Filled on F1 Initiated GA | `COUNTD(if BOOKING_FLAG = 1 and ENTRY_POINT_FLAG = 1 and FORM_1_INITIATED = 1 and FORM_1_COMPLETED = 1 then LEAD_ID end) / COUNTD(if BOOKING_FLAG = 1 and ENTRY_POINT_FLAG = 1 and FORM_1_INITIATED = 1 then LEAD_ID end)` | lead | `BOOKING_FLAG`, `ENTRY_POINT_FLAG`, `FORM_1_INITIATED`, `FORM_1_COMPLETED`, `LEAD_ID` | [[Dashboard - User To Form 1 Fill]] |
| F1 Filled on BC Backend | `COUNTD(if BOOKING_FLAG = 1 and FORM_1_FILLED_FLAG = 1 then USER_ID end) / COUNTD(if BOOKING_FLAG = 1 then USER_ID end)` | user | `BOOKING_FLAG`, `FORM_1_FILLED_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| F1 Filled on BC GA | `COUNTD(if BOOKING_FLAG = 1 and FORM_1_INITIATED = 1 and FORM_1_COMPLETED = 1 then USER_ID end) / COUNTD(if BOOKING_FLAG = 1 then USER_ID end)` | user | `BOOKING_FLAG`, `FORM_1_INITIATED`, `FORM_1_COMPLETED`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| Visit Done Users | `COUNTD(if VISIT_FLAG = 1 then LEAD_ID end)` | lead | `VISIT_FLAG`, `LEAD_ID` | [[Dashboard - User To Form 1 Fill]] |
| Login Percent of F1 | `COUNTD(if FORM_1_FILLED_FLAG = 1 and LOGIN_FLAG = 1 then USER_ID end) / COUNTD(if FORM_1_FILLED_FLAG = 1 then USER_ID end)` | user | `FORM_1_FILLED_FLAG`, `LOGIN_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| B1/B2/B3 Share on Form 2 Fill | `COUNTD(if DECILE_BUREAU_BANKING in ('B1','B2','B3') and FORM_1_FILLED_FLAG = 1 and FORM_2_FILLED_FLAG = 1 then USER_ID end) / COUNTD(if FORM_1_FILLED_FLAG = 1 and FORM_2_FILLED_FLAG = 1 then USER_ID end)` | user | `DECILE_BUREAU_BANKING`, `FORM_1_FILLED_FLAG`, `FORM_2_FILLED_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| AB Share on Form 2 Fill | `COUNTD(if LAST_RISK_BUCKET in ('A','B') and FORM_1_FILLED_FLAG = 1 and FORM_2_FILLED_FLAG = 1 then USER_ID end) / COUNTD(if FORM_1_FILLED_FLAG = 1 and FORM_2_FILLED_FLAG = 1 then USER_ID end)` | user | `LAST_RISK_BUCKET`, `FORM_1_FILLED_FLAG`, `FORM_2_FILLED_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| GC Share on Delivery | `COUNTD(if CF_COHORT = 'Good' and DELIVERY_FLAG = 1 then USER_ID end) / COUNTD(if DELIVERY_FLAG = 1 then USER_ID end)` | user | `CF_COHORT`, `DELIVERY_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| AB Share on Delivery | `COUNTD(if LAST_RISK_BUCKET in ('A','B') and DELIVERY_FLAG = 1 then USER_ID end) / COUNTD(if DELIVERY_FLAG = 1 then USER_ID end)` | user | `LAST_RISK_BUCKET`, `DELIVERY_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| B1/B2/B3 Share on Delivery | `COUNTD(if DECILE_BUREAU_BANKING in ('B1','B2','B3') and DELIVERY_FLAG = 1 then USER_ID end) / COUNTD(if DELIVERY_FLAG = 1 then USER_ID end)` | user | `DECILE_BUREAU_BANKING`, `DELIVERY_FLAG`, `USER_ID` | [[Dashboard - User To Form 1 Fill]] |
| Credit Approval Flag | `1` when `APPLICATION_DETAILS.first_credit_approved_timestamp` is not null, else `0` | loan | `CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS` | [[Analysis - Marketing Campaign Query]] |
| Disbursal Flag | `1` when `APPLICATION_DETAILS.disbursed_time` is not null, else `0` | loan | `CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS` | [[Analysis - Marketing Campaign Query]] |
| Booking Flag | `1` when `BOOKING_DETAILS.booking_time` is not null, else `0` | loan | `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS` | [[Analysis - Marketing Campaign Query]] |
| Delivery Flag | `1` when `BOOKING_DETAILS.delivery_date` is not null, else `0` | loan | `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS` | [[Analysis - Marketing Campaign Query]] |
| Form 1 Filled Flag | `MAX(LEAD_STAGE_TABLE.form_1_filled)` grouped by loan | loan | `CFSPL_NBFC_DB.PROD.LEAD_STAGE_TABLE` | [[Analysis - Marketing Campaign Query]] |
| Lookalike Credit Approval Flag | Same as `Credit Approval Flag`, used in the marketing campaign lookalike extract. | loan | `CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS.first_credit_approved_timestamp` | [[Analysis - Marketing Campaign Lookalikes]] |
| Lookalike Disbursal Flag | Same as `Disbursal Flag`, used in the marketing campaign lookalike extract. | loan | `CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS.disbursed_time` | [[Analysis - Marketing Campaign Lookalikes]] |
| Lookalike Booking Flag | Same as `Booking Flag`, used in the marketing campaign lookalike extract. | loan | `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS.booking_time` | [[Analysis - Marketing Campaign Lookalikes]] |
| Lookalike Delivery Flag | Same as `Delivery Flag`, used in the marketing campaign lookalike extract. | loan | `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS.delivery_date` | [[Analysis - Marketing Campaign Lookalikes]] |
| Lookalike Form 1 Filled Flag | `MAX(lst.form_1_filled)` grouped by `ad.loan_id`, used in the marketing campaign lookalike extract. | loan | `CFSPL_NBFC_DB.PROD.LEAD_STAGE_TABLE.form_1_filled` | [[Analysis - Marketing Campaign Lookalikes]] |
| F1-to-D Form 1 Filled Flag | From the F1-to-D base: use `cfd.form_1_filled` when `(cfd.FORM_1_FILLED = 1 and LEAD_FILL_SOURCE = 'saarthi')` or when `(cfd.FORM_1_FILLED = 1 and datediff(day, cfd.LEAD_CREATION_DATE, VISIT_TIME) between -1 and 9999 and LEAD_FILL_SOURCE = 'simpler')`. | lead/visit | `STG_F1_ATTEMPTED_BASE`, `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Form 2 Filled Flag | Same source-aware logic as Form 1 Filled, using `cfd.form_2_filled`. | lead/visit | `STG_F1_ATTEMPTED_BASE`, `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Form 3 Filled Flag | Same source-aware logic as Form 1 Filled, using `cfd.form_3_filled`. | lead/visit | `STG_F1_ATTEMPTED_BASE`, `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Banking Required Flag | Uses `BR.banking_required` when banking required is true and the lead-fill-source/date-alignment condition is satisfied. | lead/visit | `STG_BANKING_REQUIRED`, `STG_F1_ATTEMPTED_BASE`, `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Banking Attempted Flag | Uses `cfd.BANKING_INITIATED` when banking initiated is true and the lead-fill-source/date-alignment condition is satisfied. | lead/visit | `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Banking Success Flag | Uses `cfd.banking_success` when banking success is true and the lead-fill-source/date-alignment condition is satisfied. | lead/visit | `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Login Flag | `cfd.login_flag` when `cfd.LOGIN_FLAG = 1`. | lead/visit | `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Credit Assessed Flag | `1` when `cfd.CREDIT_ASSESSED_STATUS` is not null, else `0`. | lead/visit | `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Credit Approved Flag | `1` when `cfd.CREDIT_ASSESSED_STATUS = 'Credit Approved'`; when assessed but not approved, `0`. | lead/visit | `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D FCU Flag | `1` when `cfd.LATEST_FCU_APPROVED_TIMESTAMP` is not null and credit approved flag is `1`, else `0`. | lead/visit | `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D TNC Accepted Flag | `1` when `cfd.TNC_ACCEPTED_TIMESTAMP` is not null, else `0`. | lead/visit | `STG_CF_DETAILS`, `TNC_ACCEPTED_BASE` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Agreement Flag | `1` when `aggdtls.latest_agreement_date` is not null, else `0`. | lead/visit | `CFSPL_CF_C2C_DB.PRE_PROD.AGREEMENT_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Disbursal Flag | For UCC leads, `1` when `bd.DISBURSAL_FLAG = 1`; for non-`UCC1` leads, `1` when `cfd.disbursed_time` is not null; else `0`. | lead/visit | `STG_DISBURSAL_DATA`, `STG_CF_DETAILS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Token Flag | `1` when `token_time` is not null. | lead/visit | `STG_TOKEN_STATS`, `TOKEN_DETAILS_GS` | [[Reference Query - F1 to D ETL Base]] |
| F1-to-D Asset Attached | `1` when `lba.asset_attach_timestamp` is not null, else `0`. | lead/visit | `LEAD_LEVEL_MOST_RELEVANT_BOOKING_AND_ASSET_VW_TEMP_2` | [[Reference Query - F1 to D ETL Base]] |
| Agreement on Date Flag | For rolling calendar date, `1` when TEL event type is `AGREEMENT` and event date equals calendar date | booking/application/date | `TASK_EXECUTION_LOG`, `GS_SALES`, `BOOKING_DETAILS` | [[Analysis - Agreement Predictor]] |
| Credit Approved on Date Flag | For rolling calendar date, `1` when TEL event type is `CREDIT_APPROVED` and event date equals calendar date | booking/application/date | `TASK_EXECUTION_LOG`, `GS_SALES`, `BOOKING_DETAILS` | [[Analysis - Agreement Predictor]] |
| Active Tokens on Date | Rolling token cohort count based on token booking, expiry, and NRT cancellation state | booking/date | `CAPL_GS_DB.PROD.GS_SALES`, `CFSPL_NBFC_DB.PROD.BOOKING_DETAILS` | [[Analysis - Agreement Predictor]] |
| BOF Total Cohort Leads | Distinct BOF journey leads after removing stage/step/tracking/reach/completion filters; calendar and cohort-source context remains. | lead | `BOF_DIY_STEP_FACT` | [[Dashboard - DIY BOF]] |
| BOF Overall Completed Leads | Distinct cohort leads at step order 11 with completed flag 1 (Agreement Signing completion). | lead | `BOF_DIY_STEP_FACT` | [[Dashboard - DIY BOF]] |
| BOF Overall Completion % | Overall completed leads divided by total cohort leads; blank for a zero denominator. | lead | `BOF_DIY_STEP_FACT` | [[Dashboard - DIY BOF]] |
| BOF Friction Events | Row count of tracked friction/rework event rows. | friction event | `BOF_DIY_FRICTION_FACT` | [[Dashboard - DIY BOF]] |
| FCU Auto-Verified % | At loan-and-page grain, auto-approved modules divided by all approved or auto-approved modules, ignoring any existing status filter. | loan/page module | `datasource` | [[Dashboard - FCU Checks Automations]] |
| FCU API Success Rate | API request rows with exact success status divided by all API request rows in current context. | API request | `apiData` | [[Dashboard - FCU Checks Automations]] |
| WhatsApp Sent Count | Distinct delivery recipients with a nonblank sent value in the current calendar context. | recipient | `WhatsApp Delivery` | [[Dashboard - Whatsapp CRM Adoption]] |
| WhatsApp Delivered Count | Distinct delivery recipients with a nonblank delivered value in the current calendar context. | recipient | `WhatsApp Delivery` | [[Dashboard - Whatsapp CRM Adoption]] |
| WhatsApp Read Count | Distinct delivery recipients with a nonblank read value in the current calendar context. | recipient | `WhatsApp Delivery` | [[Dashboard - Whatsapp CRM Adoption]] |
| AIRO Conversation Initiation Share | Current-stage distinct funnel users divided by the distinct users at Conversations initiated, retaining date and other non-stage filters. | anonymized user / funnel stage | `airo_new_funnel` | [[Dashboard - Whatsapp CRM Adoption]] |

## Partial Metrics

| Metric/Area | Why Partial | Artifact |
|---|---|---|
| Large pasted SQL staging metrics | Many staged columns are visible, but the artifact is too broad to certify every metric without targeted review. | [[Analysis - NBFC DWH Enrichment Handoff]] |
| Same-day UCC FCU completion count | Source and filter are explicit, but this is an ad hoc monitoring query using `current_date`; not a stable metric definition until date grain and timezone convention are confirmed. | [[Analysis - Marketing Campaign Lookalikes]] |
