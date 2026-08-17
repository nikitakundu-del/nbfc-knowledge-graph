# Schema - Power BI Whatsapp CRM Adoption

Type: semantic schema

Confidence: Trusted for documented model structure.

## Core Semantic Tables And Relationships

- `WhatsApp Delivery`: delivery activity fact; active many-to-one, one-direction relationship from sent date to `Calendar[Date]`.
- `airo_funnel`: session-level AIRO funnel fact; active relationship from session-created date to `Calendar[Date]`.
- `airo_new_funnel`: anonymized user × funnel-stage fact; active relationship from session-created date to `Calendar[Date]`.
- `Calendar`: shared reporting date dimension.

## Connected Knowledge

- [[Dashboard - Whatsapp CRM Adoption]]
- [[Metrics - Power BI Semantic Metrics]]
- [[Analysis - Whatsapp CRM Adoption Semantic Model]]
