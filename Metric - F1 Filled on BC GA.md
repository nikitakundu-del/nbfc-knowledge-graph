# Metric - F1 Filled on BC GA

Type: metric
Confidence: Trusted
Grain: user

## Definition

Share of booking-base users who initiated and completed Form 1 in GA.

## Tableau Formula

```text
COUNTD(if [BOOKING_FLAG] = 1 and [FORM_1_INITIATED] = 1 and [FORM_1_COMPLETED] = 1 then [USER_ID] end)
/
COUNTD(if [BOOKING_FLAG] = 1 then [USER_ID] end)
```

## Source

- [[Dashboard - User To Form 1 Fill]]

