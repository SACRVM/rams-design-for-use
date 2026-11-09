# rams-design-for-use

A Claude Code skill that applies Dieter Rams' design philosophy to how software is used: apps, tools and games alike, through every channel people use (mouse, keyboard, controller, pen, touch, voice), not only the visible interface.

Its core idea: you are designing for other people, never for yourself or for the AI, so never infer from your own knowledge, habits or abilities. It is a way of thinking, not a rulebook, and gives no fixed values; it helps the AI internalize what matters and apply it together with the person in front of the screen.

## Contents

A Claude Code plugin with one skill, in `skills/rams-design-for-use/`:

- `SKILL.md`: the philosophy, the workflow and the review format. Loaded when the skill triggers.
- `references/principles.md`: Rams' ten principles applied to operation, with failure patterns. Loaded on demand, always before a review.
- `references/braun.md`: what made Braun under Rams different, in sourced voices, and what it means for software. Loaded on demand.

## Install

In Claude Code (2.1.275 or later):

```
/plugin install rams-design-for-use --marketplace SACRVM/rams-design-for-use
```

On older versions, add the marketplace first, then install:

```
/plugin marketplace add SACRVM/rams-design-for-use
/plugin install rams-design-for-use@rams-design-for-use
```

Update with `/plugin update rams-design-for-use`.

## Sources

Rams' ten principles as published by [Vitsœ](https://www.vitsoe.com/gb/about/good-design); Rams' 1976 speech "Design by Vitsœ"; Fritz Eichler's ten theses on Braun design (1972/73); and further sources linked in `references/braun.md`. Quotations are short, attributed and marked as such; everything else is paraphrase or this skill's own application to software.

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) © SACRVM. Quoted material remains with its authors and sources.
