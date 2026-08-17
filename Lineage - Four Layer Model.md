# Lineage - Four Layer Model

Type: lineage hub

Confidence: Trusted for graph organization; individual knowledge remains governed by its own confidence marker.

## Canonical Direction

[[02_Table_Repository|Base layer]] → [[01_Metrics_Index|Metrics]] → [[04_Dashboard_Repository|Dashboards]] → [[03_Analysis_Repository|Analysis]]

Backward links are required so a user can navigate from an analysis or dashboard to the exact metric definition and supporting data objects.

## Layer Ownership

| Layer | Owns | Must Link To | Must Not Duplicate |
|---|---|---|---|
| Base | Databases, schemas, tables/views, fields, keys, grain, relationships, lineage | Metrics, dashboards, and analyses that consume the object | Metric formulas or analytical conclusions |
| Metrics | Numerator, denominator, aggregation, filters, exclusions, time logic, calculation grain | Supporting base objects; consuming dashboards and analyses | Physical schema definitions or dashboard layout |
| Dashboards | Consolidated metrics, visuals/reporting format, slicers, filters, refresh and reporting grain | Canonical metrics and base/semantic model; downstream analyses when evidenced | Metric formulas already owned by metric notes |
| Analysis | Question, scope, cohort, period, method, conclusions, and limitations | Canonical metrics, dashboards when used, and supporting base sources | Parallel metric or table definitions |

## Navigation Hubs

- Base: [[02_Table_Repository]], [[Schemas - Index]], [[Tables - Index]]
- Metrics: [[01_Metrics_Index]]
- Dashboards: [[04_Dashboard_Repository]]
- Analysis: [[03_Analysis_Repository]], [[Analyses - Index]]

## Curation Rule

Classify each new fact into one owning layer before writing. When two notes contain the same definition, preserve the better-evidenced canonical note, retain unique traceable context, and turn the other occurrence into a link or documented contextual variation.
