# Dashboard Repository

Dashboard notes own consolidated metric selection and reporting format. They reference canonical metric definitions and base/semantic schemas rather than duplicating calculation logic.

## Layer Navigation

- Base: [[02_Table_Repository]], [[Schemas - Index]], [[Tables - Index]]
- Metrics: [[01_Metrics_Index]]
- This layer: dashboards below
- Next layer: [[03_Analysis_Repository]]
- Model: [[Lineage - Four Layer Model]]

## Dashboards

| Dashboard | Tool | Confidence | Main Notes |
|---|---|---|---|
| [[Dashboard - User To Form 1 Fill]] | Tableau | Trusted for extracted calculated fields | TWBX XML exposed custom SQL and Tableau formulas. |
| [[Dashboard - FCU Checks Automations]] | Power BI | Trusted for documented semantic metrics | XMLA semantic-model read exposed DAX and relationships for core FCU metrics. |
| [[Dashboard - DIY BOF]] | Power BI | Trusted for documented semantic metrics | XMLA semantic-model read exposed BOF journey, friction, application, task, actor-bucket, and task-date logic. |
| [[Dashboard - Whatsapp CRM Adoption]] | Power BI | Trusted for documented semantic metrics | XMLA semantic-model read exposed delivery and AIRO funnel metric logic. |

## Dashboard Base Queries

| Base Query | Used By | Confidence |
|---|---|---|
| [[Evidence - F1 to D ETL Base]] | F1-to-D dashboards base | Trusted for listed flags and table lineage |
