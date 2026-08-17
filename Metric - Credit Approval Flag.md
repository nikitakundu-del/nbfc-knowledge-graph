# Metric - Credit Approval Flag

Type: metric
Confidence: Trusted
Grain: loan

## Definition

`1` when `APPLICATION_DETAILS.first_credit_approved_timestamp` is not null, else `0`.

## SQL Logic

> Executable source expression intentionally omitted from the sanitized GitHub mirror.

## Source

- [[Table - CFSPL_NBFC_DB.PROD.APPLICATION_DETAILS]]

## Used By

- [[Analysis - Marketing Campaign Query]]
- [[Analysis - Marketing Campaign Lookalikes]]
- [[Concept - Marketing Lookalike Audience]]

