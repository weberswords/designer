---
name: build-design-system
description: Help a project discover its own design aesthetic and build its own design system from scratch — when it has none, or only scattered fragments. Use when starting design work on a project without a coherent system, or when the user wants to establish one. Analyzes the target project, asks sharp questions to shape a direction, recommends options with rationale, then builds the tokens, type, color, spacing, and conventions INTO the target project's repository. There is no house baseline to impose — every value is chosen for this project. Confirm maturity with detect-design-system first.
---

# Build Design System

When a project has no design system of its own (or only scattered, inconsistent fragments), designer's job is to help *that project* find its aesthetic and build its own system — not to hand it a generic one. **Designer has no baseline design system to impose.** Every color, type choice, and spacing value is chosen for this project, and everything you produce is integrated into the **target project's repository**, not designer's.

Run `detect-design-system` first. Only build when maturity is **None** or **Partial** (for Partial, consolidate toward the strongest existing direction rather than starting over). If a coherent system already exists, use `design-audit` instead — don't rebuild what's working.

## The build loop

### 1. Ground in the project
Understand what you're designing for before proposing anything:
- Read the repo: product purpose, audience, domain, existing UI fragments, any brand assets (see `brand-kit`), competitor/reference products.
- Establish the goals — what success looks like (conversion, trust, comprehension, delight, credibility). Goals pick the aesthetic; your taste doesn't.

### 2. Facilitate the direction — ask, don't assume
A design system is the project's, so shape it *with* the user. Ask a **small number of high-leverage questions**, never a blank "what do you want" and never a long dump:
- What should someone feel in the first five seconds? (three words)
- Any products, sites, or brands whose feel you admire — or want to avoid?
- Who's the audience, and what do they need to trust or do?
- Hard constraints — accessibility-first, regulated industry, existing logo/color, platform, dark mode?
- How expressive vs. restrained; how dense vs. airy?

Then offer **2–3 concrete aesthetic directions**, described specifically (not "modern" or "clean"), each with a rationale tied to the goals. Show, don't abstract — name the type feeling, the color temperature, the density, the motion stance. Let the user react and choose; converge on one.

### 3. State the design read and get a nod
Before generating, declare it in one line:
> *"Building this as: a [kind] for [audience], with a [vibe] language — [type feeling], [color direction], [density], [motion stance]. Goal: [outcome]."*

Confirm this is right, then build.

### 4. Build the system — into the target repo
Produce a real, coherent, minimal-but-complete system and write it in the **target project's native stack** (Tailwind config, CSS custom properties, a tokens file, MUI/Chakra theme — whatever the project uses):
- **Color** — a committed brand color + neutral ramp + semantic set. Use OKLCH for even ramps. Verify contrast on real surfaces immediately (body ≥ 4.5:1, large/UI ≥ 3:1). Include dark mode if the project needs it, with token parity.
- **Type** — a display/text pairing that fits the vibe, a scale, weights, line-height and tracking habits, sensible fallbacks.
- **Space** — a consistent scale (usually 4px base) and a density stance.
- **Shape** — one radius language, applied consistently (this is where "consistent rounding" is decided).
- **Elevation** — borders vs. shadows, softness, layering rules.
- **Motion** — durations and easings (ease-out enters, ease-in exits), a restraint stance, reduced-motion behavior.
- **Foundational components/conventions** — the handful of primitives the project needs (button, input, card, surface), following the tokens so the system is adoptable, not just documented.
- **Documentation** — a short `DESIGN.md` (or the project's convention) in the target repo capturing the system and the *why*, so the team and future sessions can extend it consistently.

Keep it a coherent small system, not a 40-page guide. Ship tokens + a few primitives + a page of docs.

### 5. Make it living
- Everything lands in the target project's repo, wired into its build — not in designer.
- Leave the system consistent and extensible so the next component fits without a decision.
- Note open questions and proposed-but-unconfirmed choices explicitly rather than inventing.

## Where the other skills fit
- `brand-kit` — capture or define the project's identity; the system encodes it as tokens.
- `ux-principles` — the quality floor every system must clear.
- `impeccable`, `taste-skill`, `emil-design-skills` — reach into these for craft, taste direction, and motion detail while building. They raise quality; they don't decide the project's identity — the project does.

## The one rule
Never impose a generic or reused aesthetic. Two projects built with this skill should end up looking like themselves, not like each other. If you catch yourself reaching for a default palette, type pairing, or the last project's system, stop and go back to the read.
