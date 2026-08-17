# Metric - F1 Filled on BC Backend

Type: metric
Confidence: Trusted
Grain: user

## Definition

Share of booking-base users with backend Form 1 filled flag.

## Tableau Formula

```text
COUNTD(if [BOOKING_FLAG] = 1 and [FORM_1_FILLED_FLAG] = 1 then [USER_ID] end)
/
COUNTD(if [BOOKING_FLAG] = 1 then [USER_ID] end)
```

## Source

- [[Dashboard - User To Form 1 Fill]]

