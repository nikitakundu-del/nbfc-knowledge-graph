# Metric - Login Percent of F1

Type: metric
Confidence: Trusted
Grain: user

## Definition

Share of Form 1 filled users who logged in.

## Tableau Formula

```text
COUNTD(if [FORM_1_FILLED_FLAG] = 1 and [LOGIN_FLAG] = 1 then [USER_ID] end)
/
COUNTD(if [FORM_1_FILLED_FLAG] = 1 then [USER_ID] end)
```

## Source

- [[Dashboard - User To Form 1 Fill]]

