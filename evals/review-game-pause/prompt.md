---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Please review the pause and menu handling of our game for how players will use it. You cannot run it; the relevant facts and code are below.

Ember Climb is a deliberately hard precision platformer: you die a lot and retry at once. It is sold for PC and consoles and most players use a controller. Two things are design pillars and are not up for change: there are no difficulty settings, and the wall-dash is performed by holding Grab and pressing Jump. That combination is the core mechanic and is taught in the first room.

```js
const bindings = { jump: ['Space', 'pad:A'], grab: ['ShiftLeft', 'pad:RT'], move: ['Arrows', 'pad:stick'] };

// Pause
window.addEventListener('keydown', e => { if (e.code === 'Escape') togglePause(); });

const pauseItems = ['Resume', 'Restart room', 'Quit to title'];
function openPause() {
  menu.innerHTML = pauseItems.map(t => `<div class="item" onclick="act('${t}')">${t}</div>`).join('');
}
function act(t) {
  if (t === 'Resume') togglePause();
  if (t === 'Restart room') restartRoom();
  if (t === 'Quit to title') location.href = 'title.html';
}

// Progress is saved only when a chapter is finished (a chapter is 15 to 25 rooms).
// title.html offers: Continue, New game, Settings (volume, screen shake, key remapping).
// On death the room restarts after 0.4 s.
```
