# Dashboard - User To Form 1 Fill

Confidence: Trusted for extracted calculated fields and visible custom SQL sources.

## Tool

Tableau packaged workbook (`.twbx`).

## Primary Sources Observed

- [[Table - CFSPL_CF_C2C_DB.PROD.F1_TO_D_DASHBOARD_VW]]
- [[Table - CFSPL_CF_C2C_DB.PROD.U2FORM_FILL]]
- [[Table - CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT.CUSTOMER_CREDIT_VARIABLES]]
- [[Table - CSPL_MKT_DB.MKT_BI.BUYER_LAST_TOUCH_FINAL]]

## Reference Base Query

- [[Reference Query - F1 to D ETL Base]] is the source reference query used for the F1-to-D dashboard base.

## Workbook Filters Observed

One visible custom SQL block filters:

- `lead_type = 'Asset Addition'`
- `lead_channel = 'C2C'`

## Trusted Tableau Calculations

See [[01_Metrics_Index#Trusted Metrics]] for formulas promoted from this dashboard.

Metric hub: [[Metrics - Tableau Dashboard Rates]]

## Important Fields

- `ENTRY_POINT_FLAG`
- `FORM_1_INITIATED`
- `FORM_1_COMPLETED`
- `FORM_1_FILLED_FLAG`
- `FORM_2_FILLED_FLAG`
- `BOOKING_FLAG`
- `DELIVERY_FLAG`
- `LOGIN_FLAG`
- `VISIT_FLAG`
- `USER_ID`
- `LEAD_ID`
- `LAST_RISK_BUCKET`
- `DECILE_BUREAU_BANKING`
- `CF_COHORT`

## Notes

The workbook also includes categorization logic for CF entry points and entry point labels. Those are potentially valuable dimensions, but should be promoted after reviewing the full mapping list.
