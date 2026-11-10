---
type: llm
weight: 1
---

PASS only if the script explicitly handles a notes file that exists but contains invalid JSON (for example catches json.JSONDecodeError or equivalent) and tells the user what happened without destroying the file silently. FAIL if invalid JSON would crash with a traceback or be overwritten without notice.
