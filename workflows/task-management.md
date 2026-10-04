# Task Management Workflows

> **Status:** Planned Technical Specification

## 1. Planned Operations
* **Task Ingestion & Parsing:** Extracts tasks from natural language prompts, incoming emails, or manual quick-add inputs.
* **Dynamic Prioritization:** Computes priority scores based on:
  $$	ext{Priority Score} = w_1 \cdot 	ext{Deadline Urgency} + w_2 \cdot 	ext{Estimated Effort} + w_3 \cdot 	ext{Course Weight}$$
* **Decomposition:** Breaks large multi-hour assignments into atomic subtasks (e.g., *Literature Review*, *Draft Methodology*, *Format Citations*).
* **Backlog Recovery:** Identifies overdue or stagnant tasks and proposes automatic rescheduling into open calendar blocks.

## 2. n8n Node Implementation Plan
* `Webhook`: Ingests task creation requests.
* `Postgres Node`: Reads current user backlog from `tasks` table.
* `Code Node`: Evaluates prioritization formula.
* `Todoist Node`: Creates task items with labels and due dates.
* `Postgres Node`: Writes assigned task IDs into memory.
