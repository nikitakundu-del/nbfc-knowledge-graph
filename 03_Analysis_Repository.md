# Analysis Repository

Node hub: [[Analyses - Index]]

Analysis notes own recurring reporting and one-time analytical questions, scope, cohorts, periods, methods, conclusions, and limitations. They reference canonical metrics and base objects instead of redefining them.

## Layer Navigation

- Base: [[02_Table_Repository]], [[Schemas - Index]], [[Tables - Index]]
- Metrics: [[01_Metrics_Index]]
- Dashboards: [[04_Dashboard_Repository]]
- This layer: analyses below
- Model: [[Lineage - Four Layer Model]]

| Analysis | Business Question / Purpose | Confidence | Notes |
|---|---|---|---|
| [[Analysis - Agreement Predictor]] | Rolling token-to-agreement and credit approval view. | Trusted for listed flags | SQL explicitly creates temp tables and source logic. |
| [[Analysis - Marketing Campaign Query]] | Customer/application features for marketing campaign targeting or analysis. | Trusted for listed fields | Source tables and field logic are explicit. |
| [[Analysis - Marketing Campaign Lookalikes]] | Loan-level customer/funnel extract for campaign lookalike audience building, plus supporting source-check queries. | Trusted for loan-level extract; partial for ad hoc checks | Query was pasted directly in chat and matches the existing marketing campaign extract. |
| [[Analysis - U2FF Query ETL]] | User-to-Form-Fill funnel ETL across entry points, GA behavior, bookings, and marketing mix. | Trusted for source tables; partial for all derived fields | SQL is explicit, but many funnel fields need business naming review before stakeholder publication. |
| [[Evidence - F1 to D ETL Base]] | Reference ETL query used as the F1-to-D dashboard base. | Trusted for listed flags and table lineage | Supplied as a DOCX query artifact; source logic is explicit. |
| [[Analysis - Lead Stage Snapshot]] | Daily active lead stage snapshot, especially DS/final offer terms. | Trusted for offer-term lineage | Strong in-query comments document validated appointment linkage. |
| [[Analysis - NBFC DWH Enrichment Handoff]] | DWH enrichment handoff and validation methodology. | Partial | Excellent system context, but not all generated columns are present as final stakeholder metric definitions. |
| [[Analysis - Task TAT and Queue]] | Task queue, pickup, hold, and completion TAT. | Partial | Source fields are visible, but formulas should be reviewed by funnel owner before reuse. |
| [[Analysis - SMS Risk and Feature Stamping]] | SMS risk bucket and feature stamping timing. | Partial | Data sources are explicit; business/privacy review recommended before broad graph publishing. |
| [[Analysis - FCU Employment Check Logic]] | Latest FCU employment-check extraction and API/review outcome classification. | Trusted | Worksheet SQL explicitly exposes tables, join keys, flattening, filters, grain, and category precedence. |
| [[Analysis - BOF GA Funnel Semantic Model]] | BOF journey, friction, and application-outcome semantic model. | Trusted | Model structure and core DAX measures are explicitly available. |
| [[Analysis - BOF Task Actor Model]] | BOF task volume, completion, actor-bucket, and task-date reporting. | Trusted | Model partitions, relationships, grain, and exact measures are explicit. |
| [[Analysis - Whatsapp CRM Adoption Semantic Model]] | WhatsApp delivery and AIRO conversation-funnel semantic model. | Trusted | Model relationships and core DAX measures are explicitly available. |
