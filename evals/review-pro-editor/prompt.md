---
max_turns: 12
timeout_seconds: 480
allowed_tools: [Read, Glob, Grep, Skill]
---

Please review the command set of our video editor for how people will use it. CutBench is for professional editors who work in it eight hours a day. Two things are deliberate team decisions and stay: single-key shortcuts (J/K/L shuttle, I/O marks, B blade, N snapping), and the dense timeline. You cannot run it; the table below is the specification.

| Command | Menu | Shortcut | Toolbar |
|---|---|---|---|
| Play / shuttle | Playback > Shuttle | J K L | none |
| Mark in / out | Mark > In, Mark > Out | I, O | none |
| Blade | Edit > Blade | B | icon, tooltip "Blade (B)" |
| Ripple delete | none | Shift+Alt+X | none |
| Undo | Edit > Undo | Ctrl+Z | none |
| Export | File > Export… | Ctrl+E | icon, no tooltip, no label |
| Snapping on/off | View > Snapping | N | icon, looks the same on and off |
| Autosave | none | none | runs every 10 minutes without any sign; a failed autosave is written to a log file only |
