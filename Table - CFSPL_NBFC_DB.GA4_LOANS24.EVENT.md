# Table - CFSPL_NBFC_DB.GA4_LOANS24.EVENT

Layer: Base

Confidence: Trusted.

## Grain and Role

Event-row source for the BOF DIY lead cohort and proxy-action journey. The semantic model limits the relevant cohort to proxy actions from 2026-06-01 onward.

## Trusted Fields and Relationships

- Event date supplies cohort and event-date context.
- The Loans24 lead identifier connects event rows to the BOF lead journey and to `CFSPL_NBFC_DB.PROD.TASK_EXECUTION_LOG.entity_identifier`.
- Event name identifies the proxy-action cohort used by the BOF task model.

## Consumers

- [[Schema - Power BI DIY BOF]]
- [[Analysis - BOF GA Funnel Semantic Model]]
- [[Analysis - BOF Task Actor Model]]

Source traceability: Power BI semantic model `DIY BOF Dashboard` partition lineage read 2026-08-20.
