# Dashboard - DIY BOF

Confidence: Trusted for documented semantic-model measures and relationships.

## Semantic Model

- Power BI workspace: `NBFC -Product`
- Semantic model: `DIY BOF Dashboard`
- Core journey fact: `BOF_DIY_STEP_FACT`, one row per lead and configured step.
- Friction fact: `BOF_DIY_FRICTION_FACT`.
- First-step fact: `BOF_DIY_FIRST_STEP_FACT`, one row per lead and started stage.
- Application fact: `APPLICATION_DETAILS`, loaded from Snowflake and limited to disbursal time on or after 15-Jun-2026.

## Trusted Measures

- **Total Cohort Leads**: distinct BOF journey leads while removing stage-, step-, tracking-, reach-, and completion-status filters; calendar and cohort-source filters remain.
- **Overall Completed Leads**: distinct cohort leads whose step order is 11 and completed flag is 1; the model identifies this as Agreement Signing completion.
- **Overall Completion %**: overall completed leads divided by total cohort leads; blank when the cohort denominator is zero.
- **Journey Completion %**: uses completion-after-reach in step context and stage-completion-after-start in stage context.
- **Friction Events**: row count of the friction fact.
- **Disbursed Applications**: distinct application loan ids in the model's disbursed-date scope.

## Source Traceability

- Semantic-model metadata and DAX read through the Power BI XMLA endpoint on 2026-08-12.

## Connected Knowledge

- Metrics: [[Metrics - Power BI Semantic Metrics]] and [[01_Metrics_Index]]
- Semantic schema: [[Schema - Power BI DIY BOF]]
- Analysis: [[Analysis - BOF GA Funnel Semantic Model]]
