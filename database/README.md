# Database Layer: PostgreSQL / Supabase

> **Status:** Schema Defined — See [schema.md](schema.md)

## Purpose
Acts as the persistent memory layer for OPHELIA, storing:
* `users` and `user_preferences`
* `tasks` and deadlines
* `calendar_events_twin` (cached Google Calendar mirror)
* `workflow_history` (immutable audit trail with rollback tokens)
