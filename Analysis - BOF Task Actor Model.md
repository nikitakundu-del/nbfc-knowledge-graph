# Analysis - BOF Task Actor Model

Layer: Analysis

Confidence: Trusted.

## Question and Scope

Supports reporting on task-execution volume, distinct BOF leads or applications with tasks, completed tasks, actor-bucket mix, and task-activity-date trends for the BOF DIY cohort from 2026-06-01 onward.

## Method and Grain

- `BOF_DIY_TASK_ACTOR_FACT` supports task-execution-row and distinct-lead reporting.
- The BOF-scoped semantic `TASK_EXECUTION_LOG` supports source task-log-row and distinct-application reporting.
- Alternate date measures activate each task table's inactive task-activity-date relationship to Calendar.
- Actor-bucket reporting uses a lead-level bridge. Buckets are not mutually exclusive across a lead's task history.

## Canonical Dependencies

- Base: [[Table - CFSPL_NBFC_DB.GA4_LOANS24.EVENT]], [[Table - CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG]], [[Schema - Power BI DIY BOF]]
- Metrics: [[Metrics - BOF Task Actor]]
- Dashboard: [[Dashboard - DIY BOF]]

## Limitations

The semantic definitions establish calculation behavior but do not establish a business target or service-level interpretation. Distinct actor/applicant counts are not promoted as canonical metrics until their intended reporting meaning is explicit.

Source traceability: Power BI semantic model `DIY BOF Dashboard`, partitions, relationships, calculated actor bridge, and exact measures read 2026-08-20.
