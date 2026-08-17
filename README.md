# NBFC Knowledge Graph

Private, sanitized GitHub mirror of the Obsidian knowledge graph used for NBFC analytics.

The graph connects dashboards, metrics, semantic and source schemas, tables, and analysis logic through Obsidian wiki links. The local Obsidian vault remains the source of truth.

## Mirror safety

- Hidden sync checkpoints and local Obsidian session state are excluded.
- Dedicated source-query notes and executable SQL, DAX, M, or Power Query blocks are omitted from this mirror.
- Credentials, tokens, query results, extracts, and raw business-data exports must never be committed.
- Daily syncs are additive and must never force-push or change repository visibility.

Start with `00_Home.md` or `Graph - Relationship Map.md`.
