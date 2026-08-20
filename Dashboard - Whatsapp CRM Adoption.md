# Dashboard - Whatsapp CRM Adoption

Confidence: Trusted for documented semantic-model measures and relationships.

Layer: Dashboard

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
- **Conversion from conversations initiated**: exact semantic-model alias of **% of conversations initiated**. Both names resolve to the canonical [[Metric - AIRO Conversation Initiation Share]]; the dashboard does not own a second definition.

## Source Traceability

- Semantic-model metadata and DAX read through the Power BI XMLA endpoint on 2026-08-12.
- The new alias and its exact definition were read through XMLA on 2026-08-20 and matched the existing measure definition exactly.

## Connected Knowledge

- Base/semantic schema: [[Schema - Power BI Whatsapp CRM Adoption]]
- Metrics: [[Metric - AIRO Conversation Initiation Share]], [[Metrics - Power BI Semantic Metrics]] and [[01_Metrics_Index]]
- Dashboard: this note
- Analysis: [[Analysis - Whatsapp CRM Adoption Semantic Model]]

Graph model: [[Lineage - Four Layer Model]].
