# BOF GA Funnel Semantic Model

Confidence: Trusted.

## Purpose

Transforms the BOF journey semantic layer into a lead × configured-step funnel with Profile, Verification, and Mandate stages, including friction/rework analysis and application outcomes.

## Trusted Lead-Journey Logic

Confidence: Trusted.

- Grain: one row per loan lead in the hidden lead-journey layer before expansion to configured steps.
- Cohort start: the first explicit BOF proxy event; when absent, the first observed downstream journey event is used and identified as an inferred cohort source.
- Only events at or after the lead's cohort timestamp contribute to journey milestones.
- Profile completion requires explicit completion evidence for KYC, additional information, and document upload; its timestamp is the latest of those required component completions.
- Verification completion requires explicit completion evidence for VPD, reference submission/completion, and motor-insurance completion; its timestamp is the latest of those required component completions.
- Agreement completion uses the agreement-signed timestamp when present and otherwise the KFS-continue timestamp.
- Friction/rework is counted from an explicit event set covering document deletion, repeated company-email OTP/manual entry, VPD photo retakes, motor-insurance removal/retry, and VKYC restart.
- Lead-level flags record which milestones were reached, and elapsed-time fields measure minutes from cohort start to profile completion, verification completion, and KFS continuation.

## Connected Knowledge

- [[Dashboard - DIY BOF]]
- [[Metrics - Power BI Semantic Metrics]]
- [[Schema - Power BI DIY BOF]]
- [[Analysis - FCU Employment Check Logic]]

## Source Traceability

- Power BI semantic model `DIY BOF Dashboard`, read 2026-08-12.
- Snowflake worksheet execution `01c64b6e-0002-73d8-0008-3056269004ee`, executed 2026-08-10T10:54:09.482Z; reviewed 2026-08-17. No source SQL or row values are stored here.
