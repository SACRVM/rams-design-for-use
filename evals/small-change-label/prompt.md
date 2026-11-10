---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

In this component, change the button label from "Submit" to "Send invoice". Reply with the changed file.

```jsx
export function InvoiceActions({ onSend, onDiscard, busy }) {
  return (
    <div className="invoice-actions">
      <button type="button" onClick={onDiscard} disabled={busy}>Discard draft</button>
      <button type="submit" onClick={onSend} disabled={busy}>Submit</button>
    </div>
  );
}
```
