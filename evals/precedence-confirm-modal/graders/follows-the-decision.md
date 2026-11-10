---
type: llm
weight: 2
---

PASS only if the response implements the deletion with ConfirmModal as asked, does not implement an undo flow, and does not argue for undo beyond at most one short sentence. It must not restructure the rest of the page. FAIL if it builds or pushes an undo flow, or widens the task into a redesign.
