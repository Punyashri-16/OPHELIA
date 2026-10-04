# Data Flow Diagram (DFD) — Level 0: Context Level

## 1. Overview
The **Level 0 Context Diagram** defines the external boundary of the **OPHELIA Automation System**, highlighting all external entities that interact with OPHELIA and the major data flows exchanged between them.

---

## 2. Mermaid Level 0 Diagram

```mermaid
flowchart TD
    User([👤 User / Knowledge Worker])
    Cal([📅 Google Calendar Service])
    Mail([📧 Email / Inbox Service])
    Tasks([📝 Task Management API
Todoist / Notion])
    Notify([🔔 Notification Channel
Push / Webhook])
    
    subgraph OPHELIA_Boundary [OPHELIA AUTOMATION SYSTEM]
        OPHELIA((OPHELIA Core
AI Reasoning + n8n Orchestrator
+ PostgreSQL Memory))
    end

    %% User Data Flows
    User -->|1. Natural Language Commands| OPHELIA
    User -->|2. Action Approvals / Modifications| OPHELIA
    User -->|3. Preferences & Configuration| OPHELIA
    OPHELIA -->|4. Active Schedule & Priority Feed| User
    OPHELIA -->|5. Proactive Intervention Cards| User
    OPHELIA -->|6. Execution Audit & Rollback Status| User

    %% Calendar Service Flows
    OPHELIA -->|7. Query Existing Events & Free Slots| Cal
    Cal -->|8. Calendar Event Metadata & State| OPHELIA
    OPHELIA -->|9. Create / Update / Reschedule Events| Cal
    Cal -->|10. Event Confirmation & Event IDs| OPHELIA

    %% Email Service Flows
    Mail -->|11. Ingest Raw Emails & Assignment Notices| OPHELIA
    OPHELIA -->|12. Acknowledge / Read Status| Mail

    %% Task Management Service Flows
    OPHELIA -->|13. Fetch Active Task Backlog| Tasks
    Tasks -->|14. Task Records & Due Dates| OPHELIA
    OPHELIA -->|15. Create / Prioritize / Complete Tasks| Tasks
    Tasks -->|16. Task Status & Confirmation| OPHELIA

    %% Notification Flows
    OPHELIA -->|17. Dispatch Scheduled Milestone Alerts| Notify
    Notify -->|18. Delivery Receipts| OPHELIA
```

---

## 3. External Entities & Data Flow Catalog

| Entity | Direction | Data Flow Name | Description |
| :--- | :--- | :--- | :--- |
| **User** | Inbound | `Natural Language Commands` | High-level instructions (e.g., *"Organize my week around my exam"*). |
| **User** | Inbound | `Action Approvals` | 1-click confirmation or dismissal of proposed schedule shifts. |
| **User** | Outbound | `Proactive Intervention Cards` | Contextual recommendations surfaced on the Command Center UI. |
| **Google Calendar** | Inbound | `Event Metadata & Free Slots` | Real-time state of existing meetings, classes, and appointments. |
| **Google Calendar** | Outbound | `Create / Reschedule Events` | API calls to insert optimized study blocks or move conflicting focus sessions. |
| **Email Service** | Inbound | `Assignment Notices` | Incoming syllabus updates, project announcements, and meeting invitations. |
| **Task Management API** | Inbound | `Task Records` | Existing task backlog items and their status. |
| **Task Management API** | Outbound | `Create / Update Tasks` | Synchronized task milestones decomposed from user goals. |
| **Notification Channel** | Outbound | `Scheduled Milestone Alerts`| Time-sensitive push webhooks armed 24h/4h prior to deadlines. |
