---
name: rams-ui-design
description: UI/UX guidance for apps, dev/desktop tools and games. Use when building, changing or reviewing any screen, dialog, form, menu, toolbar, settings page, HUD, onboarding, keyboard shortcuts or controller/input scheme, or when asked whether a UI is clear, cluttered, consistent or accessible. Based on Dieter Rams' ten principles.
---

# Good UI/UX Design: Dieter Rams' Ten Principles for Software and Games

This skill translates Dieter Rams' ten principles of good design into rules for applications, tools and games. **Part 1 (Core)** governs every UI task. **Part 2 (Reference)** adds per-principle detail and anti-patterns: consult it when reviewing, or when unsure how a principle applies.

The skill doesn't replace a design system. Take concrete values (type scale, colors, spacing, components) from the project. This skill makes sure they're used with purpose and consistency.

**Scope:** For a change that touches one component and adds no new flow, do steps 4–6 only, and state in one line which frequency class the touched action belongs to. Run the full workflow for new screens, new flows and reviews.

---

# Part 1: Core

## Stance

- **People first.** Rams called indifference towards people and the reality they live in "the one and only cardinal sin in design." Every decision starts with three questions: **Who** operates this, **when** do they operate it, and **why**?
- **Frequency shapes the layout.** Short paths for everyday actions. Rare actions stay out of the way, but they're never buried or made needlessly complicated.
- **Nobody should have to memorize the interface.** People arrive tired, distracted or after a long day. Recognition beats recall.
- **Depth doesn't come from variety.** A few well-combined elements beat many redundant ones, in tools and especially in games.
- **Criteria, not dogma.** Rams meant his principles to be weighed and discussed. Use judgment, not box-ticking.
- **Reduction is not a style.** Rams rejected "minimalism" as a label for his work. Reduce to serve use, not to look minimal: as simple as possible, but not simpler.
- **Design is engineering.** Rams preferred the term *Gestalt-Ingenieur*. A design that can't be built well isn't finished, and neither is code that works but confuses.
- **Think before you render.** "Design begins in our heads, not in computers."
- **Respect attention.** "Less would be better everywhere." Software should let people get done and leave.

**Attribution:** Quoted lines are Rams'. Frequency placement, recognition over recall (Nielsen), "depth not variety", the game guidance, the numeric minimums and the conflict ranking are this skill's extensions for software, not Rams' words. Never attribute them to him in reviews.

## Workflow

### Step 1: Who, when, why
Before designing, work out the human side. Derive it from the README, docs, existing UI, domain language, issue tracker and the request. Write it in **at most three lines**, not an essay:
- **Who:** role, experience, and how often (daily power user, weekly, occasional). Don't assume young, tech-savvy users with perfect eyesight and unlimited patience. Many users, and many players, are adults with jobs, families and little spare energy.
- **When:** situation and state of mind (focused desk work, a quick task between meetings, tired on the sofa in the evening, interrupted halfway), plus device, screen size and input method (mouse/keyboard, touch, gamepad).
- **Why:** the real goal behind the action ("get the invoice out and go home", "relax for an hour"), not the feature name. The goal decides what must be fast and what may take a step longer.

Then list the actions and sort them by frequency: **every session**, **regularly**, **rarely**.

If the context is unclear and a wrong guess would change the design substantially, ask one short question. Otherwise state your assumption in one line at the top of your output ("Assuming: daily-use internal tool, keyboard-heavy, desktop only") and continue.

### Step 2: Settle the concept before the pixels
Decide the flow, the information hierarchy and every state (empty, loading, error, offline, permission-denied, very long and very short content) before you write polished UI. Don't let a slick mockup hide unresolved structure.

### Step 3: Place actions by frequency

| Frequency | Placement |
|-----------|-----------|
| **Every session** | Visible and reachable in one step from the main screen: a labeled primary control or a direct gesture, with an optional single-key accelerator. No menu or dialog in between. **If more than 5–7 actions qualify, the sorting is wrong: re-rank.** Sensible defaults so that often no action is needed at all. |
| **Regularly** | At most two steps, placed next to the object it acts on (context menu, inline action, the section it belongs to), not in a global menu far away. |
| **Rarely** | In clearly grouped settings or menus with plain-language labels, out of the main flow. A search or command palette can add a second route, but never replaces browsable grouping, because it requires recalling a term. Never hidden behind obscure gestures, unlabeled icons or sub-sub-menus. |

Rules:
- **Shortcuts accelerate; they never replace.** A bare key is a shortcut, not a path. Every action must be reachable through visible, labeled UI. Show shortcuts where the action lives (menus, tooltips) so people learn them in passing.
- **No required combos for core actions.** Multi-key chords, long modifier sequences and hidden gestures are fine as optional accelerators, never as the only way.
- **Consistent mappings.** The same key or button does the same thing everywhere. A small vocabulary of actions that combine beats a large one that must be learned.
- **Recognition over recall.** Show options instead of expecting people to remember them. Keep context visible across steps, and resume where the user left off.
- **Progressive disclosure has costs.** Overflow and hamburger menus sharply reduce discoverability, so never put an everyday action there. Hover-only reveals need a touch and keyboard equivalent. "Advanced" sections remember whether they were expanded.

### Step 4: Build under constraints
- Follow the platform's and the codebase's conventions before you invent patterns.
- **Earn-its-place test:** for every element, setting, dialog or animation, name the user task from step 1 it serves. If you can't, leave it out.
- Use the project's tokens and scales for every value. Nothing arbitrary.
- Treat labels, units, number formats and microcopy as design work: verbs on buttons, and errors that say what happened and how to fix it.

**Measurable minimums:**
- **Targets:** ≥24×24 CSS px for pointer (WCAG 2.2 AA), ≥44×44 pt for touch. Frequent targets larger and near where the pointer or thumb already is (Fitts's law).
- **Response:** react within 100 ms. Show an indicator after ~1 s. Show progress plus a cancel option after ~10 s.
- **Motion:** transitions 150–250 ms, never blocking input. Respect reduced-motion settings.
- **Contrast:** 4.5:1 for text, 3:1 for large text and UI components. Focus always visible and never obscured. Never convey information by color alone.
- **Destructive actions:** confirm only irreversible ones (sent, paid, permanently deleted), and name the consequence on the button ("Delete 12 files"), never "OK". Everything reversible: do it immediately and offer undo for 5–10 s.
- **Forms:** validate on blur or submit, not on every keystroke. Never discard entered input on error or navigation.
- **Async status:** announce changes to screen readers (live region). No keyboard traps.

### Step 5: Look at it
Don't judge a UI from its code alone. Render it and inspect the result with whatever is available: a browser or screenshot tool, Playwright, or running the app and capturing a screenshot. Check at least:
- **Widths:** narrow (~360 px), medium (~768 px), wide (~1440 px). For desktop apps, small and large window sizes.
- **Themes:** light and dark, if both are supported.
- **Content stress:** very long strings, empty data, many items, and localized text. German sentences run ~30% longer than English, and short labels can double or triple.
- **Zoom and text scaling:** 200%.
- **Keyboard only:** tab through the screen; focus is visible and in a sensible order. For games, do the same with a controller.
- **Interaction states:** hover, focus, active, disabled, loading and error states actually render.
- **Path count:** walk the top everyday actions and count the steps.

Fix what you see, then look again. **If you have no way to see the result, say so explicitly.** Never claim it looks right when you haven't looked.

### Step 6: Review against the checklist
**Answer each row with evidence (a count, a named state, a measured value or a file reference), never just "yes".** If you can't produce evidence, the row is unverified: say so.

| ID | Evidence to produce |
|----|---------------------|
| Core A | Who/when/why in ≤3 lines, including how a tired or interrupted user gets through. |
| Core B | Top three everyday actions with their step counts (target: 1). Where each rare action lives, and how it's found without memorizing. |
| P1 | Each non-standard pattern, and the problem a convention couldn't solve. |
| P2 | Primary task step count; whether it works with no shortcut knowledge; whether it works without the mouse. |
| P3 | Values outside the token/scale system; decoration that costs legibility or speed. |
| P4 | Any control whose purpose isn't clear from its label; any state that isn't visible (saving, syncing, disabled and why). |
| P5 | Every interruption (modal, popup, badge, toast) and the reason it exists. |
| P6 | Anything misleading, overclaiming, attention-grabbing, or harder to undo than to do. |
| P7 | Changed conventions, shortcuts or terminology versus the previous version or platform. |
| P8 | Missing states, missing undo, keyboard/controller gaps, measured contrast and target sizes. |
| P9 | Idle cost (polling, timers, frame rate, bundle size), visual noise. |
| P10 | Elements whose removal breaks nothing; variety that adds things to learn without adding meaningful choices. |

## Tools vs. games
- A **tool** removes friction: the fastest path to the user's goal wins.
- A **game** may add *deliberate* friction where it *is* the designed challenge, including inventory limits or diegetic UI if that's the point. Pause, save/quit, settings and accessibility are always frictionless.

### Games for adults with limited time and energy
Many players are adults who play in the evening, tired from the day, in short or interrupted sessions. Design for them by default:
- **Small, consistent control vocabulary.** A handful of inputs that work context-sensitively and mean the same thing in every mode. No combos to memorize for core actions.
- **Depth from interaction, not inventory.** Depth comes from a few systems that combine in interesting ways, not from dozens of currencies, item tiers, skill trees or button combinations. If a new system mainly adds things to remember, cut or merge it.
- **Respect the session.** In single-player, a suspend-save on quit is mandatory, and checkpoints are frequent. On resume, show a one-line "where was I / what was I doing" recap plus the current control prompts. Never punish stepping away. Multiplayer and permadeath designs may restrict this deliberately, but say so up front.
- **Low memory load.** Quest goals, controls and key information can be looked up in-game at any moment.
- **Controller first.** Focus always visible, with initial focus on the most common *safe* item. The same button cancels/goes back everywhere. Button glyphs follow the active input device. No pointer-only targets. "Quit without saving" needs hold-to-confirm.
- **Couch distance.** Body text ≥ ~28 px at 1080p (readable at ~3 m), scalable, with a high-contrast HUD and subtitles on by default.
- **Onboarding.** Teach one input at a time, in play. Contextual prompts fade once mastered. Tutorials are skippable for returning players.
- **Settings baseline.** Full remapping, sensitivity, invert axes, camera shake, motion blur, FOV, separate volume sliders, colorblind modes, and difficulty changeable mid-game without penalty or shame.
- Game feel can't be judged from code: for mechanics, recommend playtesting rather than claiming a verdict.

## When principles conflict
This ranking is the skill's, not Rams':
1. Honest (6) is non-negotiable.
2. Useful (2) and Understandable (4) come before Aesthetic (3) and Minimal (10).
3. Hiding a needed function is not minimalism. Minimal means fewer *unnecessary* things, never less clarity, and rare functions still need a findable home.

## Review output format

When asked to review, report findings ordered by severity, then user impact. Skip anything you can't tie to a real user consequence.

```
[Severity: high|medium|low] <Core A|Core B|Principle N>: <short title>
Where: <screen / component / file:line>
Problem: <what the user experiences>
Fix: <concrete change>
```

- **high:** loses work, misleads, blocks a task, or excludes users (a11y failure).
- **medium:** adds steps to an everyday action, or hides a needed function.
- **low:** polish and consistency.

End with the two or three changes that would improve the experience the most, and say whether you inspected the rendered UI or only the code. If the UI is in good shape, say so briefly instead of inventing findings.

---

# Part 2: Reference, the ten principles in detail

### 1. Good design is innovative
Rams: new design only arises together with new technology and new functionality, never as restyling.
- **Tools:** Rethink workflows; don't bolt on features. Could this task need fewer steps altogether?
- **Games:** Innovation lives in mechanics and feel, not in unusual menu layouts or control schemes players must relearn.
- **Anti-patterns:** Custom scrollbars, reinvented form controls, gesture-only navigation without a visible alternative.

### 2. Good design makes a product useful
Rams: the job is not superficial polishing but making the product usable. Remove anything that gets in the way of use.
- **Tools:** Bulk actions for repeated work, fast startup, defaults that make the common case zero-click.
- **Games:** Controls respond instantly, with input buffering so presses just before an action becomes available aren't lost. Unskippable sequences and slow menus block the player.

### 3. Good design is aesthetic
"Only well-executed objects can be beautiful": appeal comes from a convincing concept and execution, not ornament.
- **Tools:** Consistent spacing scale, few type sizes, clear hierarchy.
- **Games:** The visual and audio language carries the atmosphere, and the UI matches the world's tone, as long as styling never costs legibility or speed.
- **Anti-patterns:** Mixed icon styles, decorative gradients, glows and chrome, animation that delays interaction.

### 4. Good design makes a product understandable
Rams: at best a product is self-explanatory, and explains itself without a long manual. At Braun, scales and labels on the device were core design work. In software, that work is labels, units, data display and microcopy.
- **Tools:** Immediate feedback for every action; errors that say what happened and how to fix it.
- **Games:** Teach through level design and play, not walls of text.

### 5. Good design is unobtrusive
Rams: products that serve a purpose are like tools. They should be neutral and restrained, to leave room for the user's self-expression. The user's content, and in games the player's agency, is the hero.
- **Tools:** No unprompted popups, nags, badges or "what's new" interruptions mid-task. Prefer inline, non-blocking feedback over modals.
- **Games:** Keep the HUD minimal, contextual and diegetic where sensible.
- **Anti-patterns:** Modal confirmation for reversible actions, notification spam, attention-grabbing animation on idle elements.

### 6. Good design is honest
Rams: a product must never appear more innovative, powerful or valuable than it really is, and it doesn't manipulate.
- **Tools:** Buttons do exactly what they say. Progress bars reflect real progress. Cancelling is as easy as subscribing. Privacy choices are neutral, with nothing pre-checked.
- **Overclaiming:** No inflated copy, no fake "magic" or AI framing for simple logic, no fake activity indicators or artificial delays.
- **Attention:** The user controls the software, not the other way round. No engagement-maximizing loops, streak pressure or infinite feeds in tools.
- **Games:** No manipulative monetization, loot-box odds disclosed up front, no fake scarcity timers, no daily-login pressure, no compulsion loops.
- **Anti-patterns:** Dark patterns of any kind (confirmshaming, hidden costs, disguised ads, roach-motel flows, misleading defaults).

### 7. Good design is long-lasting
Rams: good design avoids being fashionable, so it never looks dated.
- **Tools:** Keep layouts, shortcuts and terminology stable across versions. Don't break muscle memory without strong reason, and provide migration hints when you must. Don't redesign for its own sake.
- **Games:** The game still works years later: no needless always-online dependency, and saves and settings survive updates.

### 8. Good design is thorough down to the last detail
Rams: nothing must be arbitrary or left to chance, because care in the details shows respect for the user.
- **Interaction details:** Focus management, sensible tab order, preserved scroll position and input on navigation, resume after interruption.
- **Accessibility:** Screen-reader labels, scalable text, reduced motion, plus the minimums in step 4.

### 9. Good design is environmentally friendly
Respect the user's resources: CPU, memory, battery, bandwidth, storage and attention. Rams counted visual pollution as harm too, so visual noise is a cost.
- **Tools:** Small bundles, lazy loading, no needless background polling, minimal tracking, idle means idle.
- **Games:** Frame-rate caps (especially in menus), efficient pause states, scalable settings for older hardware, reasonable patch sizes.

### 10. Good design is as little design as possible
Less, but better: concentrate on the essentials and don't burden the product with non-essentials. Late in life Rams extended this to "less would be better everywhere".
- **Tools:** Fewer options with great defaults beat a settings maze. Remove before you add.
- **Games:** A few deep systems beat many shallow ones. Variety that only adds things to learn, without new meaningful choices, is not depth.
