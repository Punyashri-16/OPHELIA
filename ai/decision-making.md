# Decision-Making: Rule-Based vs. Context-Aware AI

| Evaluation Scenario | Traditional Rule-Based Automation | OPHELIA Context-Aware System |
| :--- | :--- | :--- |
| **Trigger** | Email arrives with subject containing *"Assignment 3"* | Email arrives with subject containing *"Assignment 3"* |
| **Parsing Logic** | Regex matches keyword *"Assignment"* | LLM extracts deadline (Wed 23:59), project rubric, and course weight |
| **Context Evaluated** | None (Blind execution) | Cross-references Friday exam, current 14h weekly meeting load, and stored energy habits |
| **Execution** | Creates static task with no due date | Synthesizes two 90-min non-conflicting study sprints on Mon/Tue, inserts GCal events, and arms alerts |
| **Failure Tolerance** | Collides with existing meetings; user must fix manually | Detects Thursday collision in advance and shifts work to Wednesday morning |
| **Outcome** | Notification noise and cognitive drag | **Zero friction. Situation understood, plan made, actions completed.** |
