# Schema - Power BI FCU Checks Automations

Type: semantic schema

Confidence: Trusted for documented model structure.

## Core Semantic Tables And Relationships

- `datasource`: FCU evaluation/verification fact, including loan, page, status, audit, task, and check-update attributes.
- `apiData`: API request fact; active many-to-many relationship to `datasource` on loan id.
- `task_exec_log`: task activity fact; active many-to-many relationship from `datasource` loan id to application id.
- `Auto Accepted Module Buckets`: bucket dimension with active one-direction relationship to `datasource`.
- `Calendar`: active one-direction relationship to the datasource task-updated date; additional local date dimensions support other audit/task/API timestamps.

## Connected Knowledge

- [[Dashboard - FCU Checks Automations]]
- [[Metrics - Power BI Semantic Metrics]]
- [[Analysis - FCU Employment Check Logic]]
