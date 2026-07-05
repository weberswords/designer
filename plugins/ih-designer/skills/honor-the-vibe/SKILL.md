---
name: honor-the-vibe
description: The prime directive and entry point for design work across any project. Use at the START of any UI/UX task — designing, redesigning, building a component or page, styling, theming, or reviewing an interface — to read a project's existing vibe, energy, feeling, and goals and commit to honoring them instead of flattening everything into the same generic look. Establishes the precedence order (the project's own system wins over house defaults) and routes to the right foundational skill. Not for backend or non-UI work.
---

# Honor the Vibe

The prime directive: **every project has its own vibe, energy, feeling, and goals. Your job is to honor them — not to make everything look the same.**

Most AI design output is bad for one reason: the model reaches for its default aesthetic (AI-purple gradients, centered hero on a dark mesh, three equal feature cards, Inter + slate-900, glassmorphism on everything) instead of reading what *this* project actually is and wants to be. That default is slop. It erases identity. Refuse it.

This skill runs first. It decides what the project is, what wins when styles conflict, and which foundational skill to reach for next.

## The loop

Run these in order. Don't skip to code.

### 1. Detect what already exists
Before proposing anything, find out what the project already is. Invoke **`detect-design-system`** to inventory tokens, theme files, Tailwind/CSS config, component libraries, fonts, color, spacing, radii, shadows, and motion conventions. A project with an existing system is not a blank canvas — it is a set of commitments you must respect.

### 2. Read the room
State a one-line **Design Read** before touching anything:

> *"Reading this as: a [kind] for [audience], with a [vibe] language, leaning toward [system / aesthetic family]. Goal: [what success looks like]."*

Cover, in your own head at least:
- **Kind** — marketing/landing, product UI/dashboard, portfolio, editorial, tool, docs, app shell.
- **Audience** — who uses this and what they need to feel (trust, delight, speed, focus, credibility).
- **Vibe words** — the user's ("Linear-clean", "brutalist", "warm", "premium", "playful", "serious B2B", "editorial") or the ones the existing design already speaks.
- **Energy** — loud vs. quiet, dense vs. airy, kinetic vs. still, expressive vs. restrained.
- **Goals** — conversion, comprehension, retention, showing off craft, reducing support load. The goal picks the aesthetic; your taste doesn't.

If the read genuinely diverges and you can't infer it, ask **one** sharp question — never a multi-question dump. If you can infer confidently, declare the read and proceed.

### 3. Apply the precedence order
When it's time to make visual decisions, resolve conflicts in this order — **higher wins**:

1. **The project's own design system** — its committed tokens, components, and conventions. If it exists, it is law. Identity preservation beats your preferences every time.
2. **The project's brand kit** — logo, brand color, type, voice, imagery. Use **`brand-kit`** to capture or apply it. For a redesign these are starting material, not optional.
3. **Established craft references** — reach into the bundled skills for domain expertise: `impeccable` for broad frontend craft and anti-patterns, `emil-design-skills` for motion/animation and interface detail, `taste-skill` for landing/portfolio taste and anti-slop direction. These raise quality; they don't override identity.
4. **Universal UX principles** — usability, hierarchy, accessibility, cognitive load. Use **`ux-principles`**. These are non-negotiable minimums (contrast, focus states, hit targets) but they constrain, they don't dictate style.
5. **The Intelligent Hoodlums house system** — use **`intelligent-hoodlums-design-system`** only as a *fallback* when a project has no identity of its own, or as a source of craft standards that never override 1–4.

The whole point of the order: house defaults are the last resort, not the first move. A project's own voice always wins.

### 4. Commit and ship
Make committed choices, not hedged ones. Real working code, real tokens, verified contrast, honest motion. Don't leave a design half-generic because you were unsure — resolve the read, then commit.

## Anti-slop discipline

Actively refuse the LLM defaults unless the project genuinely calls for them:
- AI-purple / indigo gradients as a crutch
- Centered hero over a dark radial mesh
- Three equal glassy feature cards
- Inter + slate-900 by reflex
- Infinite-loop micro-animations everywhere
- Generic glassmorphism on every surface
- Emoji as section icons in serious product UI

Reach past these *deliberately*, anchored to the Design Read. If you catch yourself producing a look that would fit any project equally, stop — that's the tell that you've stopped honoring this one.

## Homogenization is the failure mode

The single worst outcome is every project this toolkit touches converging on the same look. Guard against it:
- A brutalist site and a trust-first public-sector service should not end up cousins.
- Don't import the house system's personality into a project that has its own.
- Don't reuse the last project's palette, type, or motion out of habit.
- When in doubt, make the project *more* itself, not more like your default.

Difference is the deliverable. Honor the vibe.
