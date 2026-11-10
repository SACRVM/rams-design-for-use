---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Write a PostgreSQL migration that adds an index on orders(customer_id, created_at) without blocking writes on the table, plus the matching down migration. Reply with both in code blocks.
