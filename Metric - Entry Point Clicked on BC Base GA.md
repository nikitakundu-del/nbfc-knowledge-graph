# Metric - Entry Point Clicked on BC Base GA

Type: metric
Confidence: Trusted
Grain: user

## Definition

Share of booking-base users with a GA entry point click.

## Tableau Formula

```text
COUNTD(if [BOOKING_FLAG] = 1 and [ENTRY_POINT_FLAG] = 1 then [USER_ID] end)
/
COUNTD(if [BOOKING_FLAG] = 1 then [USER_ID] end)
```

## Source

- [[Dashboard - User To Form 1 Fill]]

