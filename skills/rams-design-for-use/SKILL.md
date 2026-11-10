---
name: rams-design-for-use
description: "Dieter Rams' design philosophy applied to how software is used, the ergonomics of operating apps, tools and games alike, through every channel (mouse, keyboard, controller, pen, touch, voice) and not only the visible interface. Its core: you design for other people, never for yourself, so never infer from your own knowledge, habits or abilities. Use when designing, building or reviewing anything people operate (screens, dialogs, forms, menus, toolbars, settings, HUDs, onboarding, error messages, notifications, wording and labels, shortcuts, controller, pen, touch or voice input, command-line tools, configuration), or when asked whether something is clear, usable, accessible, cluttered, confusing, inconsistent or tiring. Not for backend-only work or bug fixes with no effect on how something is operated."
---

# Designing for others: Dieter Rams' design philosophy applied to how software is used

Rams designed physical products at Braun, not software, and he wrote no rules for screens. His way of thinking about use has inspired generations of designers; Apple under Jony Ive carried it into digital products most visibly. What they took was a way of thinking, not a look to copy. This skill gives you that way of thinking, to apply to how software is used, together with the person in front of the screen.

It is about use: how easily people find, understand, reach and trust what they need, in an app, a tool or a game alike. Use is more than the visible interface. People operate software with mouse, keyboard, controller, pen, touch and voice, and through what they hear, feel and type outside any window: sounds and vibration, notifications, commands, configuration. Every one of these channels is part of the design.

This is a philosophy, not a rulebook: its purpose is to make you internalize what matters and to keep that awareness awake while you work. It gives you no fixed values (sizes, spacing, colors, timings, contrast), because good values follow from the people and their situation, not from a table.

## Scope

- **Small change** (one control, no new flow): make it, then ask once: who touches this control, and what do they not know that I do? Mention the answer only if it changes something. Nothing else here applies: no workflow, no references, no report.
- **Everything else** (new screens, new flows, explicit reviews): the whole skill.

## Precedence

The user's explicit request and the project's design system win. If they conflict with this skill, follow them and name the tension in one line. Don't widen the task into a redesign.

## References, read when needed

- `references/principles.md`: the ten principles applied to operation, with failure patterns. Always read it before an explicit review, or when unsure how a principle applies.
- `references/braun.md`: what made Braun under Rams different, in sourced voices, and what it means for software. Read it when you need the spirit behind a decision, or the person asks why.

## The one idea: you are not the user

Whatever you are working on, you are not making it for yourself, and not for the person you are building it with either. If the two of you were the only ones who ever operate it, you would not need this skill. You are making it for other people, and they are not like you.

You know things they don't:
- You know how it works inside, what every term means, and why it was built this way.
- You know where everything is, because you put it there.
- You have the full context of the task, right now, rested and focused.
- You see it on your screen, with your input device, your data, your language and your abilities.

They have none of that. They arrive tired, distracted, interrupted, after a long day, with different eyes, hands, devices and words. So:

- **Never infer from yourself to others.** "I find this obvious" or "I would just press X" is not evidence; it is the bias this skill exists to break. Knowing something makes it hard to imagine not knowing it.
- **Ask who else will operate it.** If you cannot name anyone, assume the least favorable realistic person (first time, tired, no shortcuts), say so in one line, and continue.
- **Treat every assumption about people as an assumption.** Say it out loud ("Assuming: occasional users, mostly on touch"), and check it against real people whenever you can: watching someone use it beats any argument.

Rams called indifference towards people and the reality they live in "the one and only cardinal sin in design." That indifference most often looks like designing for yourself without noticing.

## Together with the person in front of the screen

You don't apply this alone. The person you work with is the bridge to the people who will operate the result: they can try it with their own hands, watch others use it, and judge how it feels.

- State the assumption from step 1 where they will see it, so they can correct it.
- Hand over something they can run, and ask them to try the everyday actions, not to read your description.
- Their observation is a finding. If they stumble, it is the design, not their mistake; never answer "but it works if you…".
- They know the product too. When they say "that's obvious", ask the same question you ask yourself: obvious to whom?

## Stance

- **Challenge is not friction.** In a game, the difficulty is what people came for, and it stays. Getting in, pausing, saving, leaving, changing settings and finding your way around are operation, never the challenge.
- **Reduction is not a style.** "Less, but better" is Rams' aim: concentrate on the essentials. Reduce to serve use, not to look minimal.
- **Criteria, not dogma.** Rams wrote that his principles are "not set in stone" and that each generation should review them. Use judgment, not box-ticking.
- **Design is engineering.** Rams preferred the term *Gestalt-Ingenieur* to "designer". A design that can't be built well isn't finished, and neither is code that works but confuses.
- **Respect attention.** Software should let people get done, or get to the fun, and leave when they want.

**Attribution:** Only text in quotation marks is Rams' wording; principle summaries are paraphrases. "You are not the user", frequency placement, recognition over recall (Nielsen), the variety-is-not-depth rule, "challenge is not friction" and the conflict ranking are this skill's application to software. Never attribute them to Rams.

## Workflow

### 1. Who, when, why, and what they don't know
In at most four lines:
- **Who** operates it: role, experience, how often (every day, now and then, once).
- **When:** situation and state of mind (focused, rushed, tired in the evening, interrupted halfway), device and the channels they use (mouse, keyboard, controller, pen, touch, voice, often several at once or switching).
- **Why:** the real goal behind the action ("get the invoice out and go home", "relax for an hour"), not the feature name.
- **What they don't know that you do:** internal terms, hidden shortcuts, where things live, what happens next.

Then sort the actions by frequency: every session, regularly, rarely. State assumptions in one line and continue; ask one short question only if a wrong guess would waste major work.

### 2. Settle the concept before the details
Decide the flow, what matters most at each point, and every state people can meet (empty, loading, error, offline, nothing allowed, too much content), before polishing anything.

### 3. Place actions by frequency
How often people need something decides how close it is. What counts as everyday and as already known is decided by the people in step 1, not by you: a tool professionals live in all day and a game's own control grammar are learned once and may be dense; something used now and then may not.
- **Every session:** labeled, and reachable without hunting or remembering. A stable place counts (a pause menu, a platform key, the first lines of the help); don't cover the work or the play with controls.
- **Regularly:** next to the thing it acts on.
- **Rarely:** a findable home in plain-language settings or menus, reachable by browsing.
- **Shortcuts, combinations and gestures speed things up; they are never the only way in.** Show them where the action lives so people learn them in passing. Whatever is revealed only on hover, in an overflow menu or by a gesture also has a way that can be found by looking.
- **Recognition beats recall.** Nobody should have to memorize the interface. Show options, keep context visible, and resume where people left off with enough context to remind them what they were doing.
- **The same situation, the same input.** Keep the platform's meanings (confirm, cancel, undo) and never give a control a second, surprising meaning. A key may differ where the situation is visible (Enter in a text field and in a dialog).
- **A channel you offer is a full way in for what you offer it for.** Nobody who picked up a controller, a pen or their voice for the everyday actions is stranded halfway (plays but cannot pause or save; reads but cannot confirm). A channel meant for one job (pen to draw, voice to dictate) says so and hands over cleanly.

### 4. Build it with them in mind
- Follow platform and project conventions before inventing patterns: what people already know is the cheapest thing to learn.
- **Earn its place:** for every element, option, dialog or animation, name the task from step 1 it serves. If you can't, leave it out. A few elements that combine well beat many that must each be learned.
- Words are design work: verbs on buttons, labels in the users' language rather than the code's, errors that say what happened and what to do now.
- Every action gets immediate feedback people can perceive in the channel they used (seen, heard or felt), and every state stays perceivable (saving, waiting, disabled and why). Input given a moment early is not thrown away.
- Make mistakes cheap, in every channel: whatever deletes or overwrites can be undone or recovered (an undo, a trash, a kept copy), in a command line as much as in a dialog. Only where that is impossible, ask first and name exactly what will be lost. Never lose what people entered.
- Different bodies and situations: poor eyesight, shaky hands, no sound, one free hand, color blindness, a different language. Design for them from the start.
- Values come from people: when you set a size, a spacing, a timing or a contrast, derive it from the people in step 1 (how far away they are, what they hold, how well they see and hear, how tired they are) and say in one line whom it serves, so it can be checked. Platform guidelines and accessibility standards are the floor, not the goal. Where the project has a design system, work within it; where it fails these people, say so in one line.

### 5. Walk through it as them
Don't judge from the code, and don't judge as yourself. Run it, look at it, and go through the everyday actions as the person from step 1: for the first time, tired, interrupted halfway, without knowing the shortcuts, with each channel they use, their screen, their language and their data (empty, too much, long names). Count the steps to each everyday action. Look for where they would hesitate, guess or get lost.

Looking is not the whole test. Walk the everyday path with the keyboard only, and by the names and order that someone who cannot see the screen would get. Where sound or vibration carries information, walk one path without it. Looking and not seeing a problem is not evidence.

Fix what you find, then walk through again. **If you could not run or see it, say so.** Never claim it works for people when you haven't looked.

### 6. Check
With evidence, never just "yes" (a step count, a named state, where something is found, a file reference):
- **People:** who/when/why, and how a tired or interrupted person gets through.
- **Frequency:** the top everyday actions and their steps; where each rare action lives and how it is found without remembering.
- **Understanding:** controls whose purpose isn't clear from their label, name or prompt; states people cannot perceive.
- **Interruptions:** every popup, notice, badge, sound and vibration, and why it has to interrupt.
- **Honesty:** anything misleading, pushy, or harder to undo than to do.
- **Changes:** what people had learned that now works differently, and how they are helped across.
- **Essentials:** what could be removed without anyone missing it.

When building, answer in a few lines of prose, only the rows that need an answer; never paste the checklist. When reviewing, use it as your own checklist and report only findings, in the format below.

## When principles conflict
This ranking is the skill's, not Rams':
1. Honest is non-negotiable.
2. Useful and understandable come before aesthetic and minimal.
3. Hiding a needed function is not minimalism. Minimal means fewer *unnecessary* things, never less clarity.

## Review output format

Findings ordered by how much they hurt people. Skip anything you can't tie to a real consequence for someone operating it; no restyling by taste.

```
[Severity: high|medium|low] <principle or check>: <short title>
Where: <screen / component / command / setting / file:line>
Problem: <what the person experiences>
Fix: <concrete change>
```

- **high:** people lose work, are misled, get stuck, or are shut out.
- **medium:** an everyday action takes extra steps, or a needed function is hard to find.
- **low:** polish and consistency.

End with the two or three changes that would help people most, and say whether you ran and looked at it or only read the code. If it is in good shape, say so briefly instead of inventing findings.
