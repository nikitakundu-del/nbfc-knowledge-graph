# NBFC Product Analytics Knowledge Graph

Owner role: Senior Business Analyst, Product Team, CARS24 NBFC business.

Business area: financing options for used cars and customer-to-customer journeys, primarily inside the mobile app.

## Purpose

This vault stores three connected layers of knowledge:

1. Metric definitions, source tables, fields, filters, and calculation logic.
2. Table and database repository used across analyses and dashboards.
3. Analysis, RCA, ETL, and reporting artifacts across charters and projects.

## How To Use

- To understand a metric: open [[01_Metrics_Index]] or [[Metrics - Funnel Outcomes]], then follow links to the source tables and originating dashboard/query.
- To query Snowflake directly: open [[Tables - Index]] or [[02_Table_Repository]] and confirm the metric note is marked `Trusted`.
- To understand why an artifact exists: open [[Analyses - Index]], [[03_Analysis_Repository]], or [[04_Dashboard_Repository]].
- To see what still needs review: open [[06_Review_Backlog]].
- To explore the graph structure: open [[Graph - Relationship Map]].

## Node Hubs

- [[Analyses - Index]]
- [[Metrics - Funnel Outcomes]]
- [[Metrics - F1 to D Base Flags]]
- [[Metrics - Tableau Dashboard Rates]]
- [[Metrics - Power BI Semantic Metrics]]
- [[Tables - Index]]
- [[Schemas - Index]]
- [[Concepts - NBFC Product Analytics]]

## Current Trusted Areas

- User-to-Form-1 funnel metrics from the Tableau workbook [[Dashboard - User To Form 1 Fill]].
- F1-to-D dashboard base ETL reference query from [[Reference Query - F1 to D ETL Base]].
- Marketing campaign extract dimensions from [[Analysis - Marketing Campaign Query]].
- Marketing campaign lookalike audience extract from [[Analysis - Marketing Campaign Lookalikes]].
- Lead stage snapshot offer-term logic from [[Analysis - Lead Stage Snapshot]].
- Agreement predictor rolling-token flags from [[Analysis - Agreement Predictor]].
- U2FF ETL funnel flags from [[Analysis - U2FF Query ETL]].
- Power BI semantic measures and relationships from [[Dashboard - DIY BOF]], [[Dashboard - FCU Checks Automations]], and [[Dashboard - Whatsapp CRM Adoption]].

## Current Non-Authoritative Areas

- Undocumented Power BI measures or source transformations remain non-authoritative until their exact semantic definitions are read.
