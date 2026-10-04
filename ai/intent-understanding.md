# Intent Understanding & Entity Extraction

> **Status:** Planned Technical Specification

## 1. Intent Extraction Architecture
When a natural language prompt is received, the AI layer maps it to an operational intent schema.

### Example Prompt:
> *“Remind me about my chemistry assignment tomorrow evening and book 2 hours to work on it.”*

### Target JSON Schema Output:
```json
{
  "intent": "SCHEDULE_AND_REMIND",
  "entities": {
    "task_title": "Chemistry Assignment",
    "target_date": "2026-10-05",
    "duration_minutes": 120,
    "preferred_window": "evening",
    "reminder_offset_hours": 2
  },
  "safety_classification": "LOW_RISK_AUTONOMOUS",
  "required_integrations": ["google_calendar", "todoist", "notification_service"]
}
```
