# Dashboard - Whatsapp CRM Adoption

Confidence: Trusted for documented semantic-model measures and relationships.

## Semantic Model

- Power BI workspace: `NBFC -Product`
- Semantic model: `Whatsapp CRM Adoption`
- `Calendar[Date]` has active one-direction, many-to-one relationships to WhatsApp delivery sent date and the AIRO funnel session-created date.

## Trusted Measures

- **Sent Count**: distinct delivery recipients with a nonblank sent value in the current calendar context.
- **Delivered Count**: distinct delivery recipients with a nonblank delivered value in the current calendar context.
- **Read Count**: distinct delivery recipients with a nonblank read value in the current calendar context.
- **Funnel users**: distinct anonymized funnel users at the current stage.
- **% of conversations initiated**: current-stage funnel users divided by users at the `Conversations initiated` stage, after removing funnel-stage and stage-order filters while retaining date and other report filters.

## Source Traceability

- Semantic-model metadata and DAX read through the Power BI XMLA endpoint on 2026-08-12.

## Connected Knowledge

- Metrics: [[Metrics - Power BI Semantic Metrics]] and [[01_Metrics_Index]]
- Semantic schema: [[Schema - Power BI Whatsapp CRM Adoption]]
- Analysis: [[Analysis - Whatsapp CRM Adoption Semantic Model]]
