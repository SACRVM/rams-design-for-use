---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Please review this export wizard for how people will use it. It is part of an internal web tool. The bookkeepers who use it export the ledger every week, nearly always with the same period type, format and VAT setting. You cannot run it; the full source is below.

```html
<div id="wizard" role="dialog" aria-label="Export ledger">
  <p id="stepinfo"></p>
  <div id="body"></div>
  <button id="back">Back</button>
  <button id="next">Next</button>
  <button id="cancel">Cancel</button>
</div>
<div id="toast" hidden></div>

<script>
const $ = id => document.getElementById(id);
let step = 1, data = {};

function render() {
  $('stepinfo').textContent = `Step ${step} of 3`;
  if (step === 1) $('body').innerHTML =
    `<label>Period <select id="period"><option value="">Choose…</option>
       <option>This month</option><option>Last month</option><option>This quarter</option></select></label>`;
  if (step === 2) $('body').innerHTML =
    `<label>Format <select id="format"><option value="">Choose…</option>
       <option>CSV</option><option>XLSX</option><option>DATEV</option></select></label>
     <label><input type="checkbox" id="vat"> Include VAT columns</label>`;
  if (step === 3) $('body').innerHTML =
    `<p>Ready to export.</p><progress id="bar" max="100" value="0" hidden></progress>`;
  $('back').hidden = step === 1;
  $('next').textContent = step === 3 ? 'Export' : 'Next';
  $('next').disabled = step < 3;
  $('body').querySelectorAll('select').forEach(s => s.onchange = () => {
    data[s.id] = s.value;
    $('next').disabled = !s.value;
  });
  const vat = $('vat'); if (vat) vat.onchange = () => data.vat = vat.checked;
}

$('back').onclick = () => { step--; render(); };

$('next').onclick = () => {
  if (step < 3) { step++; render(); return; }
  const bar = $('bar');
  bar.hidden = false;
  const t = setInterval(() => { bar.value += 10; if (bar.value >= 100) clearInterval(t); }, 300);
  fetch('/export', { method: 'POST', body: JSON.stringify(data) })
    .then(r => r.blob())
    .then(download)
    .then(() => {
      $('wizard').hidden = true;
      $('toast').textContent = 'Done';
      $('toast').hidden = false;
      setTimeout(() => $('toast').hidden = true, 2000);
    });
};

$('cancel').onclick = () => { $('wizard').hidden = true; };
document.addEventListener('keydown', e => { if (e.key === 'Escape') $('cancel').click(); });

render();
</script>
```
