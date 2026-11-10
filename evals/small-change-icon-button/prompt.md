---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Add a delete button with a trash icon to this row component. It should call `onDelete(item.id)`. Reply with the changed file.

```jsx
import { PencilIcon, TrashIcon } from './icons';

export function ItemRow({ item, onEdit, onDelete }) {
  return (
    <li className="row">
      <span className="name">{item.name}</span>
      <button type="button" className="icon" onClick={() => onEdit(item.id)}>
        <PencilIcon />
      </button>
    </li>
  );
}
```
