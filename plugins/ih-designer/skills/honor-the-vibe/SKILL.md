---
name: honor-the-vibe
description: The prime directive and entry point for design work across any project. Use at the START of any UI/UX task — designing, redesigning, building a component or page, styling, theming, establishing or auditing a design system. Reads a project's own vibe, energy, feeling, and goals and commits to honoring them instead of flattening everything into the same generic look. designer has no house style of its own — it helps each project find and build its own. Sets the precedence order (the project's own identity always wins) and routes to the right foundational skill. Not for backend or non-UI work.
---

# Honor the Vibe

The prime directive: **every project has its own vibe, energy, feeling, and goals. designer's job is to help *that project* find and express them — not to make everything look the same.**

designer is a toolkit you point at *other* projects. It has **no baseline design system, no house aesthetic to impose.** When you work on a project — say a repo called `tide` — designer analyzes `tide`, helps shape `tide`'s design language, and integrates the result into **`tide`'s repository**, never into designer's. Two projects designer touches should end up looking like themselves, not like each other.

Most AI design output is bad for one reason: the model reaches for its default aesthetic (AI-purple gradients, centered hero on a dark mesh, three equal feature cards, Inter + slate-900, glass on everything) instead of reading what *this* project is and wants to be. That default is slop. It erases identity. Refuse it.

This skill runs first. It decides what the project is, what wins when styles conflict, and which foundational skill to reach for next.

## The loop

Run these in order. Don't skip to code.

### 1. Detect what already exists
Before proposing anything, find out what the project already is. Invoke **`detect-design-system`** to inventory tokens, theme files, Tailwind/CSS config, component libraries, fonts, color, spacing, radii, shadows, and motion, and to get a maturity verdict. A project with an existing system is a set of commitments to respect, not a blank canvas.

### 2. Read the room
State a one-line **Design Read** before touching anything:

> *"Reading this as: a [kind] for [audience], with a [vibe] language, leaning toward [direction]. Goal: [what success looks like]."*

Cover: **kind** (marketing, product UI, portfolio, editorial, tool, docs), **audience** (who, and what they need to feel), **vibe words** (the user's, or the ones the existing design already speaks), **energy** (loud/quiet, dense/airy, kinetic/still), and **goals** (conversion, comprehension, trust, delight). The goal picks the aesthetic; your taste doesn't.

If the read genuinely diverges and you can't infer it, ask **one** sharp question — never a multi-question dump. If you can infer confidently, declare the read and proceed.

### 3. Branch on maturity — honor, build, or audit
Based on the detect verdict:

- **Established system** → **honor it.** Extend it invisibly; match, don't invent. Then use **`design-audit`** to check it's applied consistently (rounding, scale, hierarchy, no boxes-in-boxes) and tighten it — without changing its identity.
- **Partial system** → consolidate toward the strongest existing direction with **`build-design-system`**, then audit.
- **No system** → **build the project its own**, with **`build-design-system`**: analyze the project, ask sharp questions, recommend directions, and construct tokens/type/color/space/conventions chosen *for this project* — integrated into the project's repo. Never hand it a generic or reused system.

For brand identity at any maturity, use **`brand-kit`**. For the quality floor, **`ux-principles`** always applies. When a decided piece of work needs its interface explored before you commit to one design, run a **`design-jam`**: it takes the brief from `product-steward` and diverges into several concepts in the project's own system before converging on one.

### 4. Apply the precedence order
When making visual decisions, resolve conflicts in this order — **higher wins**:

1. **The project's own design system** — its committed tokens, components, and conventions. If it exists, it is law. Identity preservation beats your preferences every time.
2. **The project's brand kit / brand assets** — logo, brand color, type, voice, imagery (`brand-kit`). For a redesign these are starting material, not optional.
3. **A system built with the project** — when little/none existed, the one you established *with the user for this project* (`build-design-system`).
4. **Established craft references** — `impeccable` (broad frontend craft, anti-patterns), `emil-design-skills` (motion, interface detail), `taste-skill` (landing/portfolio taste). These raise quality; they never decide the project's identity.
5. **Universal UX principles** (`ux-principles`) — usability, accessibility, hierarchy, cognitive load. Non-negotiable minimums that constrain style but don't dictate it.

Notice what's *not* here: any designer house style. There's no fallback aesthetic to drop in. The fallback for a blank project is to build *the project's own* — not to stamp a default.

### 5. Commit and ship — into the target repo
Make committed choices, not hedged ones. Real working code, real tokens, verified contrast, honest motion — all integrated into the **target project's repository**. Don't leave a design half-generic because you were unsure; resolve the read, then commit.

## Anti-slop discipline

Actively refuse the LLM defaults unless the project genuinely calls for them: AI-purple gradients, centered hero on dark mesh, three glassy feature cards, Inter + slate-900 by reflex, infinite micro-animations, glass on everything, emoji icons in serious product UI. If you catch yourself producing a look that would fit any project equally, stop — that's the tell you've stopped honoring this one.

## Homogenization is the failure mode

The single worst outcome is every project designer touches converging on the same look:
- A brutalist site and a trust-first public-sector service should not end up cousins.
- Don't reuse the last project's palette, type, or motion out of habit.
- When in doubt, make the project *more* itself, not more like some default.

Difference is the deliverable. Honor the vibe.
