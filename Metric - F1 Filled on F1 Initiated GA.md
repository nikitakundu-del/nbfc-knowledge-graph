# Metric - F1 Filled on F1 Initiated GA

Type: metric
Confidence: Trusted
Grain: lead

## Definition

Among leads that clicked an entry point and initiated Form 1, share that completed Form 1.

## Tableau Formula

```text
COUNTD(if [BOOKING_FLAG] = 1 and [ENTRY_POINT_FLAG] = 1 and [FORM_1_INITIATED] = 1 and [FORM_1_COMPLETED] = 1 then [LEAD_ID] end)
/
COUNTD(if [BOOKING_FLAG] = 1 and [ENTRY_POINT_FLAG] = 1 and [FORM_1_INITIATED] = 1 then [LEAD_ID] end)
```

## Source

- [[Dashboard - User To Form 1 Fill]]

