---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Please review this settings dialog for how people will use it. It belongs to a desktop note-taking app for non-technical users (teachers, office workers). You cannot run it; the full source is below.

```html
<div id="backdrop" hidden onclick="closeSettings()">
  <div id="settings" role="dialog" onclick="event.stopPropagation()">
    <div class="titlebar">
      <span>Settings</span>
      <div class="x" onclick="closeSettings()">×</div>
    </div>

    <label>sync_interval_ms
      <input id="interval" type="text" onblur="checkInterval()">
    </label>

    <label><input id="fts" type="checkbox"> Enable FTS reindex on cold start</label>

    <label>Signature (added to exported notes)
      <textarea id="signature" rows="3"></textarea>
    </label>

    <details id="advanced">
      <summary>Advanced</summary>
      <label>Export folder <input id="exportDir" type="text"></label>
    </details>

    <div class="buttons">
      <button id="save" onclick="save()">Save</button>
      <button id="reset" onclick="resetAll()">Reset all data</button>
    </div>
    <div id="msg"></div>
  </div>
</div>

<script>
const $ = id => document.getElementById(id);
let saved = load();

// Every field is filled from the saved settings each time the dialog opens.
function openSettings() {
  $('interval').value = saved.interval;
  $('fts').checked = saved.fts;
  $('signature').value = saved.signature;
  $('exportDir').value = saved.exportDir;
  $('backdrop').hidden = false;
  $('interval').focus();
}

function checkInterval() {
  const el = $('interval');
  const n = Number(el.value);
  if (!Number.isInteger(n) || n < 5000 || n > 3600000) {
    el.value = saved.interval;          // put the old value back
  }
}

function closeSettings() {
  $('backdrop').hidden = true;          // edits are dropped
}

function save() {
  try {
    store({
      interval: Number($('interval').value),
      fts: $('fts').checked,
      signature: $('signature').value,
      exportDir: $('exportDir').value,
    });
    saved = load();
    closeSettings();
  } catch (e) {
    $('msg').textContent = 'Error 0x2F';
  }
}

function resetAll() {
  localStorage.clear();        // deletes every note and all settings
  location.reload();
}

// While the dialog is open, Ctrl+S saves too, in addition to the Save button.
document.addEventListener('keydown', e => {
  if ($('backdrop').hidden) return;
  if (e.ctrlKey && e.key === 's') { e.preventDefault(); save(); }
});

// Enter inside the signature box makes a new line (default textarea behaviour).

// The Advanced section remembers whether it was open.
const adv = $('advanced');
adv.open = localStorage.getItem('advOpen') === '1';
adv.addEventListener('toggle', () => localStorage.setItem('advOpen', adv.open ? '1' : '0'));
</script>
```
