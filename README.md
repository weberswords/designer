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
| **`ih-designer`** | this repo | The foundational designer: detect a project's design system, honor its vibe, build the project its own system when it has none, audit an existing one, apply UX principles, and work from a brand kit. No house style — every project gets its own. |
| **`impeccable`** | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Broad frontend design fluency — one skill with ~23 commands (`polish`, `audit`, `critique`, `craft`, …) and anti-pattern detection. Ships a Node-based PostToolUse hook that lints UI edits. |
| **`taste-skill`** | [leonxlnx/taste-skill](https://github.com/leonxlnx/taste-skill) | Anti-slop taste for landing pages, portfolios, and redesigns (brutalist, minimalist, soft, redesign, brandkit, image-to-code, …). |
| **`emil-design-skills`** | [emilkowalski/skills](https://github.com/emilkowalski/skills) | Design-engineering taste from Vercel/Linear pedigree — motion, easing, animation review, and interface detail. |

### The `ih-designer` foundational skills

- **`honor-the-vibe`** — the prime directive and entry point. Reads the project, sets the precedence order (the project's own identity always wins), routes to the right skill, and refuses homogenization. **Start here.**
- **`detect-design-system`** — inspects a codebase for its existing tokens, theme, component library, type, color, space, and motion, and produces a structured Design Read with a maturity verdict.
- **`build-design-system`** — when a project has no system (or fragments), facilitates finding its aesthetic (asks questions, recommends directions) and builds its own tokens/type/color/space/conventions **into the target repo**.
- **`design-audit`** — when a system already exists, checks quality and consistency: consistent corner rounding, on-scale values, real hierarchy, no boxes-in-boxes.
- **`ux-principles`** — style-agnostic usability, accessibility, and interaction fundamentals (+ a full `ux-principles.md` checklist).
- **`brand-kit`** — capture, define, and apply a project's brand identity (+ a `brand-kit-template.md`).
- **`copy-that-moves`** — punch up flat, sterile, tech-bro, or "AI-sounding" copy into writing with a pulse, using Octalysis core drives, Paul Arden's nerve, and the surprise of classic advertising — all inside the project's own brand voice, never a house style.
- **`design-jam`** — facilitate a fast, structured ideation session that generates several interface concepts for a piece of work the product steward has already decided, then converges on one against a rubric grounded in the project's own system. Diverges before it commits, so the interface is a chosen direction, not the first idea. Pairs with `product-steward`, which supplies the brief.

> **designer has no baseline design system of its own.** You point it at a project — say a repo called `tide` — and its job is to analyze `tide`, help shape `tide`'s aesthetic, and integrate the result into **`tide`'s repository**. Two projects designer touches should end up looking like themselves, not like each other.

### How they work together

```
honor-the-vibe ─▶ detect-design-system ─▶ read the project's vibe, goals & maturity
      │                                              │
      │   branch on maturity:                        ▼
      │     Established ─▶ honor it + design-audit (tighten, don't restyle)
      │     Partial     ─▶ build-design-system (consolidate) + design-audit
      │     None        ─▶ build-design-system (create the project its own)
      │
      │   precedence when deciding (higher wins):
      │     1. project's own design system      ─▶ extend it invisibly
      │     2. project's brand kit / assets     ─▶ brand-kit
      │     3. a system built with the project  ─▶ build-design-system
      │     4. craft references                 ─▶ impeccable · taste-skill · emil
      │     5. universal UX principles          ─▶ ux-principles
      ▼
  commit & ship into the TARGET repo — real tokens, verified contrast, honest motion
```
There is no designer house style in that order. The fallback for a blank project is to build *the project's own* — never to stamp a default.

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
- `/ih-designer:build-design-system` to help a project establish its own system.
- `/ih-designer:design-audit` to check an existing system for consistency and quality.
- `/ih-designer:ux-principles` to review an interface against the fundamentals.
- `/ih-designer:brand-kit` to capture or apply a project's identity.

A typical run: add your project repo alongside `designer` in a Claude Code session, then let designer detect what's there, read the vibe, and either build the project its own system or audit the one it has — writing everything into your project's repo.

Skills from the other plugins are namespaced under their plugin (e.g. `/impeccable`, and Emil's/Leon's skills under theirs).

---

## Making it yours

`ih-designer` is authored to be edited — it encodes *how you work*, not a look to impose:

- Tune the method and questions in `build-design-system/SKILL.md` and the checks in `design-audit/SKILL.md` to match how you actually run a project.
- Adjust the fundamentals in `ux-principles/ux-principles.md` and the anti-slop stance in `honor-the-vibe/SKILL.md`.
- Add your own skills under `plugins/ih-designer/skills/<name>/SKILL.md` and they'll ship with the plugin.

It deliberately ships **no default tokens or house palette** — designer builds each project its own.

## Credits & licenses

`ih-designer` and this marketplace are MIT licensed (see [`LICENSE`](./LICENSE)). The referenced plugins remain under their own licenses and belong to their authors — see [`CREDITS.md`](./CREDITS.md):

- **impeccable** — © Paul Bakaus, Apache-2.0
- **taste-skill** — © Leon (leonxlnx), MIT
- **emilkowalski/skills** — © Emil Kowalski / Matt Pocock, MIT

This marketplace references those repos; it does not vendor or modify their code.