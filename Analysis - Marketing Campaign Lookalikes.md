# Analysis - Marketing Campaign Lookalikes

Confidence: Trusted for the loan-level extract; partial for the ad hoc supporting checks.

## Purpose

Builds a C2C loan-level extract for marketing campaign lookalike audience creation. The extract combines customer phone/profile questionnaire attributes with funnel outcome flags such as Form 1 filled, credit approval, booking, delivery, and disbursal.

## Grain

One row per `ad.loan_id`.

## Filter

- `ad.lead_channel = 'C2C'`

## Source Tables

- [[Table - CFSPL_NBFC_DB.PROD.BOOKING_DETAILS]] as `bd`
- [[Table - CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS]] as `ad`
- [[Table - CFSPL_CF_C2C_DB.PROD.F1_TO_D_DASHBOARD_VW]] as `fd`
- [[Table - CFSPL_NBFC_DB.PROD.LEAD_STAGE_TABLE]] as `lst`
- [[Table - CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT.CUSTOMER_CREDIT_VARIABLES]] as `ccv`

## Join Logic

| Join | Logic |
|---|---|
| Booking to application | `bd.lead_id = ad.loan_id` |
| F1-to-D dashboard view | `bd.lead_id = fd.lead_id and ad.loan_id = fd.lead_id` |
| Lead stage | `ad.loan_id = lst.lead_id` |
| Customer credit variables | `ad.loan_id = ccv._id` |

## Trusted Output Fields

| Field | Logic |
|---|---|
| `loan_id` | `ad.loan_id` |
| `phone` | `MAX(ccv.lead_details:phone::int)` |
| `form_1_filled_flag` | `MAX(lst.form_1_filled)` |
| `credit_approval_flag` | `MAX(CASE WHEN ad.first_credit_approved_timestamp IS NOT NULL THEN 1 ELSE 0 END)` |
| `disbursal_flag` | `MAX(CASE WHEN ad.disbursed_time IS NOT NULL THEN 1 ELSE 0 END)` |
| `booking_flag` | `MAX(CASE WHEN bd.booking_time IS NOT NULL THEN 1 ELSE 0 END)` |
| `delivery_flag` | `MAX(CASE WHEN bd.delivery_date IS NOT NULL THEN 1 ELSE 0 END)` |
| `disbursal_partner` | `MAX(ad.hpa_status)` |
| `age` | Age derived from `ccv.QUESTIONNAIRE:"date_of_birth"` using `DD/MM/YYYY`, adjusted for whether the birthday has occurred this year. |
| `yard_city` | `MAX(fd.yard_city_bucket_1)` |

## Questionnaire Attributes

These are extracted from `ccv.questionnaire`:

- `co_applicant`
- `current_emi`
- `current_work_ex`
- `employment_type`
- `gender`
- `house_type`
- `income`
- `income_proof`
- `industry_se`
- `marital_status`
- `pincode_current`
- `professional_sal_proof`
- `residence_stability`
- `total_work_ex`

## Supporting Ad Hoc Checks

These queries are useful for exploration/debugging but should not be treated as reusable stakeholder metrics yet.

### Customer Credit Variables Sample

Purpose: inspect sample records from the CCV source.

> Executable source expression intentionally omitted from the sanitized GitHub mirror.

### Token Date Volume

Purpose: check token volume by token date from `GS_SALES`.

> Executable source expression intentionally omitted from the sanitized GitHub mirror.

Note: the pasted query had `;LIMIT 10;` after a semicolon. The version above preserves intent in executable SQL form.

### Same-Day UCC FCU Completion Count

Purpose: count distinct UCC applications whose FCU check task was completed today.

> Executable source expression intentionally omitted from the sanitized GitHub mirror.

Review note: this uses IST conversion through `dateadd('minute', 330, created_at)` and `current_date`, so it is time-relative and should be documented before becoming a stable dashboard metric.

## Links

- [[Analysis - Marketing Campaign Query]]
- [[01_Metrics_Index]]
- [[02_Table_Repository]]
- [[Concept - Marketing Lookalike Audience]]
- [[Metrics - Funnel Outcomes]]
