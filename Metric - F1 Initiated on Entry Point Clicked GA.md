# Metric - F1 Initiated on Entry Point Clicked GA

Type: metric
Confidence: Trusted
Grain: lead

## Definition

Among booking-base leads with entry point clicked, share that initiated Form 1.

## Tableau Formula

```text
COUNTD(if [BOOKING_FLAG] = 1 and [ENTRY_POINT_FLAG] = 1 and [FORM_1_INITIATED] = 1 then [LEAD_ID] end)
/
COUNTD(if [BOOKING_FLAG] = 1 and [ENTRY_POINT_FLAG] = 1 then [LEAD_ID] end)
```

## Source

- [[Dashboard - User To Form 1 Fill]]

