# Metric - Entry Point Clicked on User Base GA

Type: metric
Confidence: Trusted
Grain: lead

## Definition

Share of leads with a GA entry point click.

## Tableau Formula

```text
COUNTD(if [ENTRY_POINT_FLAG] = 1 then [LEAD_ID] end)
/
COUNTD([LEAD_ID])
```

## Source

- [[Dashboard - User To Form 1 Fill]]

## Related

- [[Concept - F1 to D Funnel]]
- [[Metrics - Tableau Dashboard Rates]]

