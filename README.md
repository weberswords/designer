# designer

Your portable UI/UX **designer** for Claude Code — a plugin marketplace you add to any repo to get a designer's foundational craft plus a curated set of best-in-class design skills.

The whole thing is built around one objective:

> **Honor each project's own vibe, energy, feeling, and goals — don't make everything look the same.**

It reads what a project already is, respects its existing design system, and only reaches for house defaults when there's nothing of the project's own to honor. Difference is the deliverable.

---

## What's inside

This repo is a [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces). It ships one plugin authored here and references three excellent third-party skill sets, so installing this one marketplace gives you the whole designer.

| Plugin | Source | What it gives you |
|--------|--------|-------------------|
| **`ih-designer`** | this repo | The foundational designer: detect a project's design system, honor its vibe, apply UX principles, work from a brand kit, and fall back to the house system only when needed. |
| **`impeccable`** | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Broad frontend design fluency — one skill with ~23 commands (`polish`, `audit`, `critique`, `craft`, …) and anti-pattern detection. Ships a Node-based PostToolUse hook that lints UI edits. |
| **`taste-skill`** | [leonxlnx/taste-skill](https://github.com/leonxlnx/taste-skill) | Anti-slop taste for landing pages, portfolios, and redesigns (brutalist, minimalist, soft, redesign, brandkit, image-to-code, …). |
| **`emil-design-skills`** | [emilkowalski/skills](https://github.com/emilkowalski/skills) | Design-engineering taste from Vercel/Linear pedigree — motion, easing, animation review, and interface detail. |

### The `ih-designer` foundational skills

- **`honor-the-vibe`** — the prime directive and entry point. Reads the project, sets the precedence order (the project's own system wins), routes to the right skill, and refuses homogenization. **Start here.**
- **`detect-design-system`** — inspects a codebase for its existing tokens, theme, component library, type, color, space, and motion, and produces a structured Design Read.
- **`ux-principles`** — style-agnostic usability, accessibility, and interaction fundamentals (+ a full `ux-principles.md` checklist).
- **`brand-kit`** — capture, define, and apply a project's brand identity (+ a `brand-kit-template.md`).
- **`intelligent-hoodlums-design-system`** — the studio's house craft baseline and default tokens, used **only as a fallback** and as quality standards that never override a project's own identity.

### How they work together

```
honor-the-vibe  ──▶  detect-design-system  ──▶  read the project's vibe & goals
      │                                             │
      │            precedence (higher wins):        ▼
      │   1. project's own design system    ──▶  extend it invisibly
      │   2. project's brand kit            ──▶  brand-kit
      │   3. craft references               ──▶  impeccable · taste-skill · emil
      │   4. universal UX principles         ──▶  ux-principles
      │   5. house defaults (fallback only) ──▶  intelligent-hoodlums-design-system
      ▼
  commit & ship — real tokens, verified contrast, honest motion
```

---

## Install

In any project where you use Claude Code:

```
/plugin marketplace add weberswords/designer
```

Then install the whole designer, or pick pieces:

```
/plugin install ih-designer@designer
/plugin install impeccable@designer
/plugin install taste-skill@designer
/plugin install emil-design-skills@designer
```

Update the catalog later with:

```
/plugin marketplace update designer
```

> The three referenced plugins are fetched from their upstream GitHub repos at install time, so they stay current with their authors. `impeccable` includes a PostToolUse hook that runs a Node script to lint UI edits — install it only where Node is available and you want that behavior.

## Use

Once installed, just do design work — the skills activate by description. Or invoke explicitly:

- `/ih-designer:honor-the-vibe` to kick off any UI task the right way.
- `/ih-designer:detect-design-system` when you land in an unfamiliar codebase.
- `/ih-designer:ux-principles` to review an interface against the fundamentals.
- `/ih-designer:brand-kit` to capture or apply a project's identity.

Skills from the other plugins are namespaced under their plugin (e.g. `/impeccable`, and Emil's/Leon's skills under theirs).

---

## Making it yours

`ih-designer` is authored to be edited:

- Set your real brand in `plugins/ih-designer/skills/intelligent-hoodlums-design-system/design-tokens.md` — the brand color and type families are `TODO` placeholders; neutrals, spacing, radius, and motion are sensible defaults.
- Tune the philosophy in `philosophy.md`, and the principles in `ux-principles.md`, to match how you actually work.
- Add your own skills under `plugins/ih-designer/skills/<name>/SKILL.md` and they'll ship with the plugin.

## Credits & licenses

`ih-designer` and this marketplace are MIT licensed (see [`LICENSE`](./LICENSE)). The referenced plugins remain under their own licenses and belong to their authors — see [`CREDITS.md`](./CREDITS.md):

- **impeccable** — © Paul Bakaus, Apache-2.0
- **taste-skill** — © Leon (leonxlnx), MIT
- **emilkowalski/skills** — © Emil Kowalski / Matt Pocock, MIT

This marketplace references those repos; it does not vendor or modify their code.