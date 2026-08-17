# Table - CSPL_MKT_DB.MKT_BI.BUYER_LAST_TOUCH_FINAL

Type: table/view
Schema: [[Schema - CSPL_MKT_DB]]
Confidence: Trusted from Tableau custom SQL

## Purpose

Last-touch booking attribution source used in Tableau workbook.

## Key Fields Seen

- `booking_id`
- `source`
- `medium`
- `campaign`
- `channel_group_last_touch`
- `channel_group_1_last_touch`
- `date_time`

## Trusted Dedupe Rule

One row per booking using:

> Executable source expression intentionally omitted from the sanitized GitHub mirror.

## Used By

- [[Dashboard - User To Form 1 Fill]]

