# Backend: API Gateway & Context Dispatcher

> **Status:** Architecture Blueprint (Implementation starting in Phase 2)

## Responsibilities
* Receive user commands from the Command Center frontend.
* Retrieve grounded state (twin calendar, active tasks, habits) from PostgreSQL.
* Call the LLM reasoning engine to decompose requests into typed JSON execution schemas.
* Dispatch validated action schemas to n8n webhook endpoints.
* Stream execution logs and state updates back to the frontend via WebSockets.
