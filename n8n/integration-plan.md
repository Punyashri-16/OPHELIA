# n8n External Integration Plan

| Integration | Protocol / Auth | Planned Scope | Purpose in OPHELIA |
| :--- | :--- | :--- | :--- |
| **Google Calendar** | OAuth 2.0 | MVP Scope | Read active schedule, query open slots, create and reschedule focus blocks. |
| **Todoist / Notion** | REST API / Bearer Token | MVP Scope | Synchronize task registry, insert decomposed milestone items. |
| **PostgreSQL Database** | Direct TCP / SSL Connection | MVP Scope | State persistence for calendar twin, task backlog, user habits, and audit logs. |
| **Notification Webhooks**| HTTP POST / Web Push | MVP Scope | Dispatch time-sensitive deadline reminders 24h & 4h prior to submission. |
| **Gmail / Email** | OAuth 2.0 (IMAP/REST) | MVP Scope | Ingest incoming assignment publication notices and syllabus updates. |
| **Canvas / Blackboard LMS**| REST API / LTI | Future Scope | Automated ingestion of academic assignments and grades. |
| **Slack / Teams Bot** | Webhook / Bot Token | Future Scope | Push proactive alerts into workplace team channels. |
