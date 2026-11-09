# rams-design-for-use

A Claude Code skill that applies Dieter Rams' design philosophy to how software is used: apps, tools and games alike, through every channel people use (mouse, keyboard, controller, pen, touch, voice), not only the visible interface.

Its core idea: you are designing for other people, never for yourself or for the AI, so never infer from your own knowledge, habits or abilities. It is a way of thinking, not a rulebook, and gives no fixed values; it helps the AI internalize what matters and apply it together with the person in front of the screen.

## Contents

- `SKILL.md`: the philosophy, the workflow and the review format. Loaded when the skill triggers.
- `references/principles.md`: Rams' ten principles applied to operation, with failure patterns. Loaded on demand, always before a review.
- `references/braun.md`: what made Braun under Rams different, in sourced voices, and what it means for software. Loaded on demand.

## Install

```bash
git clone https://github.com/SACRVM/rams-design-for-use.git ~/.claude/skills/rams-design-for-use
```

Claude Code picks it up in new sessions. Update with `git -C ~/.claude/skills/rams-design-for-use pull`.

## Sources

Rams' ten principles as published by [Vitsœ](https://www.vitsoe.com/gb/about/good-design); Rams' 1976 speech "Design by Vitsœ"; Fritz Eichler's ten theses on Braun design (1972/73); and further sources linked in `references/braun.md`. Quotations are short, attributed and marked as such; everything else is paraphrase or this skill's own application to software.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) © SACRVM. Quoted material remains with its authors and sources.
