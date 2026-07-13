---
name: design-jam
description: Facilitate a fast, structured ideation session that generates several interface concepts for a piece of work that has already been decided, then converges on one. Use when a value increment, a user story, or a journey moment needs its interface explored before committing to a build, when the obvious first design feels flat, or when you want options on the table instead of the first idea that came to mind. Diverges into many rough concepts, then converges with a rubric grounded in the project's own design system and vibe. Does not decide what to build, scope, or when it ships, which is the product steward's job. Start from honor-the-vibe, and take the decided work from product-steward as the brief.
---

# Design Jam

A design jam is a short, structured session that puts several interface ideas on the table for one decided piece of work, then narrows to the one worth building. It exists because the first design that comes to mind is rarely the best one, and because committing to a single concept before exploring the space is how interfaces end up generic. The jam forces breadth before depth, then makes a real choice.

A jam works on **decided** work. It does not choose what to build, set scope, or set a date; those are the product steward's decisions (`product-steward`). The jam takes a value increment, a BDD story, or a journey moment that the steward has already shaped, and explores how it should look and behave. Everything the jam produces lands in the **target project's repo**, in the project's own design system, not in designer's.

## Before the jam: get the brief

A jam without a brief drifts into decoration. Anchor it first:

- **Take the decided work from the steward.** The input is a value increment or a story with its persona, its journey moment, and its "so that." If that context is missing, stop and get it from `product-steward` rather than inventing who the user is or why this matters. The jam designs the *how*, not the *what*.
- **Read the project's own system.** Run `detect-design-system` (via `honor-the-vibe`) so every concept is drawn in the project's real tokens, type, and components. A jam that ignores the existing system produces concepts that cannot be built without restyling the whole product.
- **State the design question as a how-might-we.** Turn the story into one sharp question: *"How might [persona] [do the thing] so that they feel [the outcome], here in [this project's] language?"* This is what the concepts answer.

## The jam

### 1. Diverge: many rough concepts, no judgement yet
Generate several genuinely different concepts for the interface, fast and rough. The goal is range, not polish:
- Push for distinct *approaches*, not variations on one layout. Vary the structure, the primary interaction, what leads, and what the person does first. If three concepts differ only in color, they are one concept.
- Keep them low fidelity: named directions with a quick sketch of the layout and the key interaction, in the project's tokens. Words and boxes are enough at this stage. Do not build production components yet.
- Refuse the reflex defaults called out in `honor-the-vibe`: the centered hero on dark mesh, three glassy cards, Inter by habit. A concept that would fit any project is not a concept for this one.
- Aim for at least three to five real options before you let yourself narrow. If a Miro board is available and wanted, it is a good place to host the divergent set; otherwise a short doc of named concepts works fine.

### 2. Converge: score against a rubric, do not just pick a favorite
Narrow with a small, explicit rubric so the choice is a decision, not a preference:
- **Honors the vibe.** It reads as this project, in this project's own system. This is the prime directive and it wins (`honor-the-vibe`).
- **Serves the journey moment.** It delivers the persona's "so that" at the moment the story names, and it fits how they feel there (from the steward's `user-journeys`).
- **Clears the UX and accessibility bar.** It meets `ux-principles`: hierarchy, cognitive load, keyboard reach, contrast, honest states. A beautiful concept that fails a keyboard is out.
- **Is feasible in the real system.** It can be built from the project's existing tokens and components without a rebuild, or it names the small addition it needs.

Score the concepts against the rubric, talk through the trade-offs, and pick one. A jam that ends with "they were all nice" has not finished; converging is the point.

### 3. Commit: one direction, with its reasons and its runners-up
Write up the outcome so the build can start and the thinking is not lost:
- **The chosen concept**, described concretely, in the project's system, with why it won on the rubric.
- **The strongest ideas from the runners-up** worth grafting into the winner, so a good idea in a rejected concept is not thrown away.
- **What it needs from the system**, if anything: a new component, a token, a pattern, handed to `build-design-system` or `design-audit` as follow-up.
- Land this in the target project's repo (a short design note in its `docs/`, or directly as low-fi component sketches in its stack), ready to be built into the real thing.

## Solo or with others
webs often jams alone, and the structure holds either way. Solo, the divergence is you deliberately generating options you would not have committed to, and the convergence is the rubric keeping you from just building the first idea. With others, the same phases run as a facilitated session: diverge silently first so the loudest voice does not anchor everyone, then score together. The rubric is what keeps a group jam from becoming a popularity contest.

## The boundary, held both ways
- The jam does **not** reopen what the steward decided. If the jam surfaces that the work itself is wrong (the story serves the wrong moment, the increment is too big), that is feedback *back to* `product-steward`, not a decision the jam makes on its own.
- The jam does **not** set priority, sequence, or dates. It explores the interface for work already chosen.
- The steward hands over decided work; the jam hands back a chosen interface direction. Each stays at its own altitude.

## Where the other skills fit
- `honor-the-vibe` runs first and sets the precedence every concept obeys.
- `detect-design-system` grounds the concepts in the real system.
- `ux-principles` is the bar in the convergence rubric.
- `build-design-system` and `design-audit` pick up anything the chosen concept needs the system to add.
- `apply-color`, `impeccable`, `taste-skill`, and `emil-design-skills` sharpen the chosen direction once it is picked.
- `product-steward` supplies the brief and receives any feedback that the decided work needs rethinking.

## The one rule
Diverge before you converge, and converge on purpose. A jam that skips straight to one polished idea is just designing the first thing you thought of, which is the habit the jam exists to break.
