# Review Backlog

Items here should not be treated as stakeholder-ready definitions yet.

## Needs Metric Owner Review

- Task TAT metrics: queue time, pickup time, hold time, pickup-to-complete time, total TAT. Source SQL is visible, but final business definitions should confirm stage inclusion/exclusion and sendback handling.
- SMS risk and feature stamping metrics: source tables and flags are visible, but these may touch sensitive customer-derived data and need explicit access/publishing review.
- Broad DWH enrichment staged columns from the large pasted SQL: many columns are extractable, but each should be promoted one by one with grain, source, and validation evidence.

## Needs Technical Extraction

- Power BI dashboard: extract Power Query/M, DAX measures, relationships, and model tables from `FCU checks automations dashboard.pbix`.
- Tableau workbook: full workbook formulas were partially extracted. Promote additional Tableau fields only when caption, formula, and source field lineage are clear.

## Needs Business Naming Cleanup

- Decide standard naming for `F1`, `Form 1`, `F1 Fill`, and `Basic Details`.
- Decide standard naming for `BC`, `booking cohort`, and `booking customer` if those differ.
- Decide whether `Good Cohort`, `GC`, `AB`, and `B1/B2/B3` should be exposed as stakeholder-facing names or internal analyst names.

