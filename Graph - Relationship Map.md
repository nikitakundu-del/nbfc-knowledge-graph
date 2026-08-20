# Graph - Relationship Map

Type: graph map

## Main Flow

[[Lineage - Four Layer Model]] defines the canonical ownership flow:

[[02_Table_Repository|Base layer]] → [[01_Metrics_Index|Metrics]] → [[04_Dashboard_Repository|Dashboards]] → [[03_Analysis_Repository|Analysis]]

## Trusted Cross-Layer Paths

- [[Schema - Power BI DIY BOF]] → [[Metrics - Power BI Semantic Metrics]] → [[Dashboard - DIY BOF]] → [[Analysis - BOF GA Funnel Semantic Model]].
- [[Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG]] and [[Table - CFSPL_NBFC_DB.GA4_LOANS24.EVENT]] → [[Schema - Power BI DIY BOF]] → [[Metrics - BOF Task Actor]] → [[Dashboard - DIY BOF]] → [[Analysis - BOF Task Actor Model]].
- [[Schema - Power BI FCU Checks Automations]] → [[Metrics - Power BI Semantic Metrics]] → [[Dashboard - FCU Checks Automations]] → [[Analysis - FCU Employment Check Logic]].
- [[Schema - Power BI Whatsapp CRM Adoption]] → [[Metrics - Power BI Semantic Metrics]] → [[Dashboard - Whatsapp CRM Adoption]] → [[Analysis - Whatsapp CRM Adoption Semantic Model]].
- [[Schema - Power BI Whatsapp CRM Adoption]] → [[Metric - AIRO Conversation Initiation Share]] → [[Dashboard - Whatsapp CRM Adoption]] → [[Analysis - Whatsapp CRM Adoption Semantic Model]].
- [[Schema - CFSPL_CF_C2C_DB.PROD]] → [[Metrics - Tableau Dashboard Rates]] → [[Dashboard - User To Form 1 Fill]] → [[Analysis - U2FF Query ETL]].
- [[Schema - CFSPL_CF_C2C_DB.PRE_PROD]] → [[Metrics - F1 to D Base Flags]] → [[Dashboard - User To Form 1 Fill]].
- [[Schema - CFSPL_NBFC_DB.PROD]] → [[Metrics - Funnel Outcomes]] → [[Analysis - Marketing Campaign Query]] and [[Analysis - Marketing Campaign Lookalikes]].

## Supporting Concept Paths

- [[Concept - Marketing Lookalike Audience]] frames [[Analysis - Marketing Campaign Lookalikes]], which consumes canonical base and funnel knowledge.
- [[Concept - F1 to D Funnel]] frames [[Metrics - F1 to D Base Flags]] and [[Dashboard - User To Form 1 Fill]].
- [[Concept - Task Execution]] supports [[Analysis - Agreement Predictor]], [[Analysis - Task TAT and Queue]], and [[Analysis - FCU Employment Check Logic]].
- [[Concept - Offer Terms]] supports [[Analysis - Lead Stage Snapshot]].

## Schema Hubs

- [[Schema - CFSPL_NBFC_DB.PROD]]
- [[Schema - CFSPL_NBFC_DB.GA4_LOANS24]]
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
- [[Metrics - BOF Task Actor]]
