# AI Intelligence Layer: The Brain of OPHELIA

## 1. Architectural Role
In OPHELIA, the LLM is **never used to directly call external APIs**. 

LLMs are probabilistic and prone to hallucinations; allowing an LLM to directly execute network requests creates security vulnerabilities, duplicate transactions, and unpredictable API payloads.

Instead, OPHELIA follows a strict separation of concerns:
$$\mathbf{LLM} = 	ext{Pure Reasoning, Intent Parsing, and Plan Decomposition}$$
$$\mathbf{n8n} = 	ext{Deterministic, Validated, and Audited Workflow Execution}$$

```text
User Request / Background Alert
             ↓
[ LLM: Understand Intent & Extract Entities ]
             ↓
[ Context Engine: Ground in PostgreSQL Memory ]
             ↓
[ LLM: Synthesize Deterministic Execution Schema ]
             ↓
[ Safety Filter: Validate Schema & Risk Level ]
             ↓
[ n8n: Execute Atomic Multi-Step Workflows ]
```
