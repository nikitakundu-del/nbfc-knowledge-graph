# Dashboard - FCU Checks Automations

Confidence: Trusted for documented semantic-model measures and relationships.

Layer: Dashboard

## Tool

Power BI (`.pbix`).

## What Was Extracted

The package exposes report metadata and a report page named `Monthly Task Stats`.

The connected semantic model additionally exposes explicit DAX and relationships for the following:

- **Unique loans**: distinct loan ids in `datasource`.
- **Auto-verified %**: at loan-and-page grain, counts modules with `AUTO APPROVED` status divided by all modules with `APPROVED` or `AUTO APPROVED` status; status filters are removed before evaluating the status condition.
- **Manually-verified %**: uses the same denominator, with only `APPROVED` modules in the numerator.
- **API success / failure rate**: each is API request rows in its exact status divided by all API request rows in current context.
- **Auto-accepted bucket loans**: distinct loan ids, coalesced to zero to retain empty buckets.

`apiData[LOAN_ID]` and `datasource[LOAN_ID]` are connected by an active many-to-many relationship. `datasource[LOAN_ID]` also has an active many-to-many relationship to `task_exec_log[APPLICATION_ID]`. The model has active one-direction date relationships for audit, task, API, and task-log timestamps.

## What Was Not Reliably Extracted

- Power Query/M source queries
- DAX measures
- model relationships
- table schemas
- refresh source details

## Rule

The semantic model was read through the Power BI XMLA endpoint on 2026-08-12. The documented measures may be reused with their stated filter behavior; other report elements still require targeted semantic extraction.

## Supplemental Trusted SQL

[[Analysis - FCU Employment Check Logic]] supplies one worksheet-derived FCU employment-check extraction with explicit sources, joins, filters, grain, and classification logic. It does not establish Power BI model measures.

## Connected Knowledge

- Base/semantic schema: [[Schema - Power BI FCU Checks Automations]]
- Metrics: [[Metrics - Power BI Semantic Metrics]] and [[01_Metrics_Index]]
- Dashboard: this note
- Analysis: [[Analysis - FCU Employment Check Logic]]

Graph model: [[Lineage - Four Layer Model]].
