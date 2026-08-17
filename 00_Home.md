# NBFC Product Analytics Knowledge Graph

Owner role: Senior Business Analyst, Product Team, CARS24 NBFC business.

Business area: financing options for used cars and customer-to-customer journeys, primarily inside the mobile app.

## Purpose

This vault stores four connected layers of knowledge in canonical dependency order:

1. **Base layer** — databases, schemas, tables/views, fields/columns, keys, grain, relationships, and source lineage.
2. **Metrics** — reusable definitions with explicit calculation logic, filters, time windows, exclusions, and grain.
3. **Dashboards** — consolidated canonical metrics and their reporting formats, filters, visuals, and reporting grain.
4. **Analysis** — recurring reporting and one-time analyses with explicit questions, scope, cohorts, methods, conclusions, and limitations.

Definitions live in their lowest owning layer. Dashboards and analyses link to canonical metric and base notes instead of repeating their definitions. See [[Lineage - Four Layer Model]].

## How To Use

- To understand the physical data foundation: open [[02_Table_Repository]], [[Schemas - Index]], or [[Tables - Index]].
- To understand a calculation: open [[01_Metrics_Index]] or a metric hub, then follow its base-layer links and consuming dashboards/analyses.
- To understand a reporting product: open [[04_Dashboard_Repository]], then follow its metrics backward and analyses forward.
- To understand a recurring report or one-time question: open [[03_Analysis_Repository]] or [[Analyses - Index]].
- To see what still needs review: open [[06_Review_Backlog]].
- To explore the graph structure: open [[Graph - Relationship Map]].

## Node Hubs

- Base: [[02_Table_Repository]], [[Schemas - Index]], [[Tables - Index]]
- Metrics: [[01_Metrics_Index]], [[Metrics - Funnel Outcomes]], [[Metrics - F1 to D Base Flags]], [[Metrics - Tableau Dashboard Rates]], [[Metrics - Power BI Semantic Metrics]]
- Dashboards: [[04_Dashboard_Repository]]
- Analysis: [[03_Analysis_Repository]], [[Analyses - Index]]
- Lineage: [[Lineage - Four Layer Model]], [[Graph - Relationship Map]]
- Concepts: [[Concepts - NBFC Product Analytics]]

## Canonical Layer Ownership

- Base notes own physical and semantic source structure.
- Metric notes own reusable calculation logic.
- Dashboard notes own metric composition and reporting format.
- Analysis notes own analytical questions, scope, method, and findings.

The same definition should not be rewritten in multiple layers. Context-specific differences are documented where they occur and linked back to the canonical definition.

## Existing Metric Hubs

- [[Metrics - Funnel Outcomes]]
- [[Metrics - F1 to D Base Flags]]
- [[Metrics - Tableau Dashboard Rates]]
- [[Metrics - Power BI Semantic Metrics]]

## Current Trusted Areas

- User-to-Form-1 funnel metrics from the Tableau workbook [[Dashboard - User To Form 1 Fill]].
- F1-to-D dashboard base ETL reference query from [[Evidence - F1 to D ETL Base]].
- Marketing campaign extract dimensions from [[Analysis - Marketing Campaign Query]].
- Marketing campaign lookalike audience extract from [[Analysis - Marketing Campaign Lookalikes]].
- Lead stage snapshot offer-term logic from [[Analysis - Lead Stage Snapshot]].
- Agreement predictor rolling-token flags from [[Analysis - Agreement Predictor]].
- U2FF ETL funnel flags from [[Analysis - U2FF Query ETL]].
- Power BI semantic measures and relationships from [[Dashboard - DIY BOF]], [[Dashboard - FCU Checks Automations]], and [[Dashboard - Whatsapp CRM Adoption]].

## Current Non-Authoritative Areas

- Undocumented Power BI measures or source transformations remain non-authoritative until their exact semantic definitions are read.
