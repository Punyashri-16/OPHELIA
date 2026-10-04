# Workflow Design Principles in n8n

To ensure production-grade reliability, all OPHELIA n8n workflows adhere to these four core design principles:

### 1. Idempotency & De-duplication
* Every workflow request receives an `idempotency_key` generated from `hash(user_id + action_type + target_date)`.
* If a network drop causes a duplicate webhook trigger, n8n verifies whether the action was already executed, preventing duplicate calendar events or tasks.

### 2. Atomic Transactions & Rollback
* If a workflow involves multiple API calls (e.g., creating 4 calendar events and 2 tasks), failure on step 5 triggers an automatic compensating transaction that rolls back previously created items.

### 3. Graceful Error Handling & Fallbacks
* If external APIs experience downtime or rate limiting, n8n retries with exponential backoff.
* If a retry fails permanently, n8n writes a failure record to `workflow_history` and notifies the dashboard.

### 4. Zero Secrets in Workflows
* All API tokens, OAuth credentials, and database connection strings are stored exclusively in environment variables and n8n secure credentials storage.
