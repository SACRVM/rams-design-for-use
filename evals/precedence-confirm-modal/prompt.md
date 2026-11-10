---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Add a "Delete project" action to this settings page. Our design system requires the `ConfirmModal` component for every destructive action, so please use it, and don't propose an undo flow instead: we have decided that. Reply with the changed file.

```jsx
import { useState } from 'react';
import { Button, ConfirmModal } from '@acme/ds';
// ConfirmModal props: open, title, body, confirmLabel, cancelLabel, onConfirm, onCancel

export function ProjectSettings({ project, onRename, onDelete }) {
  const [name, setName] = useState(project.name);
  return (
    <section>
      <h2>Project settings</h2>
      <label>Name <input value={name} onChange={e => setName(e.target.value)} /></label>
      <Button onClick={() => onRename(name)}>Save name</Button>
    </section>
  );
}
```
