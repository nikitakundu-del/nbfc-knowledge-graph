# Graph - Relationship Map

Type: graph map

## Main Flow

[[Concepts - NBFC Product Analytics]]

[[Concept - Marketing Lookalike Audience]] uses [[Analysis - Marketing Campaign Lookalikes]], which reads [[Table - CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS]], [[Table - CFSPL_NBFC_DB.PROD.BOOKING_DETAILS]], [[Table - CFSPL_CF_C2C_DB.PROD.F1_TO_D_DASHBOARD_VW]], [[Table - CFSPL_NBFC_DB.PROD.LEAD_STAGE_TABLE]], and [[Table - CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT.CUSTOMER_CREDIT_VARIABLES]].

[[Concept - F1 to D Funnel]] uses [[Reference Query - F1 to D ETL Base]] and powers [[Dashboard - User To Form 1 Fill]].

[[Concept - Task Execution]] supports [[Analysis - Agreement Predictor]], [[Analysis - Task TAT and Queue]], and same-day FCU checks in [[Analysis - Marketing Campaign Lookalikes]].

[[Concept - Offer Terms]] supports [[Analysis - Lead Stage Snapshot]].

[[Dashboard - DIY BOF]] → [[Metrics - Power BI Semantic Metrics]] → [[Schema - Power BI DIY BOF]] → [[Analysis - BOF GA Funnel Semantic Model]].

[[Dashboard - FCU Checks Automations]] → [[Metrics - Power BI Semantic Metrics]] → [[Schema - Power BI FCU Checks Automations]] → [[Analysis - FCU Employment Check Logic]].

[[Dashboard - Whatsapp CRM Adoption]] → [[Metrics - Power BI Semantic Metrics]] → [[Schema - Power BI Whatsapp CRM Adoption]] → [[Analysis - Whatsapp CRM Adoption Semantic Model]].

## Schema Hubs

- [[Schema - CFSPL_NBFC_DB.PROD]]
- [[Schema - CFSPL_CF_C2C_DB.PROD]]
- [[Schema - CFSPL_CF_C2C_DB.PRE_PROD]]
- [[Schema - CAPL_GS_DB.PROD]]
- [[Schema - CFSPL_NBFC_DB.PROD_MONGO_FIN_SAARATHI_BFF_DB]]
- [[Schema - CFSPL_NBFC_DB.PROD_MONGO_CF_CREDIT]]
- [[Schema - Power BI DIY BOF]]
- [[Schema - Power BI FCU Checks Automations]]
- [[Schema - Power BI Whatsapp CRM Adoption]]

## Metric Hubs

- [[Metrics - Funnel Outcomes]]
- [[Metrics - F1 to D Base Flags]]
- [[Metrics - Tableau Dashboard Rates]]
- [[Metrics - Power BI Semantic Metrics]]
