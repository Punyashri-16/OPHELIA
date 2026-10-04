# Calendar Automation Workflows

> **Status:** Planned Technical Specification

## 1. Planned Operations
* **Free Slot Discovery:** Scans the calendar twin state for non-conflicting time windows matching requested duration.
* **Deep Work Buffer Insertion:** Automatically inserts 15–30 minute buffers before and after intense study sessions.
* **Conflict Resolution:** Detects overlapping commitments and generates alternative non-conflicting slots.
* **Approval-Gated Modification:** Shifts existing meetings only after receiving explicit user authorization.

## 2. n8n Node Implementation Plan
* `Google Calendar Node (List Events)`: Queries target time range.
* `Code Node (Slot Finder)`: Executes interval intersection algorithm to pinpoint open slots.
* `Google Calendar Node (Create Event)`: Creates formatted events with color-coded tags.
* `Postgres Node`: Commits updated event IDs to `calendar_events_twin`.
