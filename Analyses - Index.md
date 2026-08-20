# Analyses - Index

Type: analysis hub

Layer: Analysis

Navigation: [[Lineage - Four Layer Model]] ← [[04_Dashboard_Repository]] ← [[01_Metrics_Index]] ← [[02_Table_Repository]]

## Analysis Nodes

- [[Analysis - Marketing Campaign Lookalikes]]
- [[Analysis - Marketing Campaign Query]]
- [[Analysis - U2FF Query ETL]]
- [[Analysis - Agreement Predictor]]
- [[Analysis - Lead Stage Snapshot]]
- [[Analysis - Task TAT and Queue]]
- [[Analysis - SMS Risk and Feature Stamping]]
- [[Analysis - NBFC DWH Enrichment Handoff]]
- [[Evidence - F1 to D ETL Base]]
- [[Analysis - FCU Employment Check Logic]]
- [[Analysis - BOF GA Funnel Semantic Model]]
- [[Analysis - BOF Task Actor Model]]
- [[Analysis - Whatsapp CRM Adoption Semantic Model]]

## Main Relationship Paths

- [[Schema - CFSPL_NBFC_DB.PROD]] → [[Metrics - Funnel Outcomes]] → [[Analysis - Marketing Campaign Lookalikes]]
- [[Schema - CFSPL_CF_C2C_DB.PRE_PROD]] → [[Metrics - F1 to D Base Flags]] → [[Dashboard - User To Form 1 Fill]]
- [[Schema - CFSPL_CF_C2C_DB.PROD]] → [[Metrics - Tableau Dashboard Rates]] → [[Dashboard - User To Form 1 Fill]] → [[Analysis - U2FF Query ETL]]
- [[Schema - CFSPL_NBFC_DB.PROD_CONVERSION_OFFER_DB]] → [[Concept - Offer Terms]] → [[Analysis - Lead Stage Snapshot]]
- [[Schema - Power BI DIY BOF]] → [[Metrics - BOF Task Actor]] → [[Dashboard - DIY BOF]] → [[Analysis - BOF Task Actor Model]]
