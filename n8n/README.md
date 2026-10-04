# n8n Automation Engine: The Execution Backbone

## 1. Why n8n?
While the LLM serves as the reasoning brain, **n8n** provides the production-grade automation infrastructure:
* **Visual Workflow Debugging:** Full visibility into execution traces, payload structures, and error states.
* **Extensive Native Connectors:** Out-of-the-box integration with Google Calendar, Todoist, Gmail, Webhooks, and PostgreSQL.
* **Self-Hostable & Privacy Preserving:** Can run in Docker environments with zero third-party telemetry on sensitive schedule data.
* **Conditional Branching & Human-in-the-Loop:** Native pause nodes waiting for user approval webhooks.

---

## 2. Planned Workflow Architecture

```text
n8n/
├── README.md
├── integration-plan.md
└── workflows/
    ├── wf-academic-week-organizer.json   (To be created in prototype phase)
    ├── wf-proactive-conflict-monitor.json (To be created in prototype phase)
    └── wf-calendar-rescheduler.json      (To be created in prototype phase)
```
