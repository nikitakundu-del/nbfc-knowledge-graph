# Metric - Visit Done Users

Type: metric
Confidence: Trusted
Grain: lead

## Definition

Distinct leads with visit flag.

## Tableau Formula

```text
COUNTD(if [VISIT_FLAG] = 1 then [LEAD_ID] end)
```

## Source

- [[Dashboard - User To Form 1 Fill]]

