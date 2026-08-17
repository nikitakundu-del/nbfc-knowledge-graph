# Analysis - Marketing Campaign Query

Confidence: Trusted for listed fields and flags.

## Purpose

Creates a loan-level feature extract for C2C leads with customer questionnaire attributes and downstream funnel flags.

This is also reused as the base structure for [[Analysis - Marketing Campaign Lookalikes]].

## Grain

One row per `ad.loan_id`.

## Filters

- `ad.lead_channel = 'C2C'`

## Source Tables

- [[Table - CFSPL_NBFC_DB.PROD.BOOKING_DETAILS]] as `bd`
- [[Table - CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS]] as `ad`
- [[Table - CFSPL_CF_C2C_DB.PROD.F1_TO_D_DASHBOARD_VW]] as `fd`
- [[Table - CFSPL_NBFC_DB.PROD.LEAD_STAGE_TABLE]] as `lst`
- [[Table - CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT.CUSTOMER_CREDIT_VARIABLES]] as `ccv`

## Trusted Fields

| Field | Logic |
|---|---|
| `phone` | `MAX(ccv.lead_details:phone::int)` |
| `form_1_filled_flag` | `MAX(lst.form_1_filled)` |
| `credit_approval_flag` | `MAX(CASE WHEN ad.first_credit_approved_timestamp IS NOT NULL THEN 1 ELSE 0 END)` |
| `disbursal_flag` | `MAX(CASE WHEN ad.disbursed_time IS NOT NULL THEN 1 ELSE 0 END)` |
| `booking_flag` | `MAX(CASE WHEN bd.booking_time IS NOT NULL THEN 1 ELSE 0 END)` |
| `delivery_flag` | `MAX(CASE WHEN bd.delivery_date IS NOT NULL THEN 1 ELSE 0 END)` |
| `disbursal_partner` | `MAX(ad.hpa_status)` |
| `yard_city` | `MAX(fd.yard_city_bucket_1)` |
| `age` | Derived from `ccv.QUESTIONNAIRE:"date_of_birth"` with birthday adjustment. |

## Questionnaire Attributes

The query extracts co-applicant, current EMI, work experience, employment type, gender, house type, income, income proof, industry, marital status, current pincode, professional salary proof, residence stability, and total work experience from `CUSTOMER_CREDIT_VARIABLES.questionnaire`.

## Links

- [[01_Metrics_Index]]
- [[02_Table_Repository]]
- [[Analysis - Marketing Campaign Lookalikes]]
- [[Metrics - Funnel Outcomes]]
