---
name: design-audit
description: Evaluate an existing design or design system for quality and consistency, and report concrete fixes. Use when a project already has a design system or built UI and you want to check whether it holds together — consistent corner rounding, values on the scale, tokens vs. one-off colors, real visual hierarchy, and no lazy patterns like boxes-nested-in-boxes or everything-is-a-gray-card. Produces a prioritized findings list with specific fixes that get integrated into the target project's repository. Run detect-design-system first to know what the system is before judging whether it's applied well.
---

# Design Audit

When a project already has a design system or a built-out UI, designer's job shifts from building to **evaluating**: does it actually hold together, and is it applied consistently and well? Run `detect-design-system` first to learn what the system *is*; this skill judges how well it's *used*. Findings and fixes are integrated into the **target project's repository**.

## What to check

### 1. Consistency (is the system actually followed?)
- **Corner radius** — is rounding consistent, or do buttons/cards/inputs/modals each use a different value? Are there stray `border-radius` values off the radius scale?
- **Spacing** — are margins/paddings/gaps on the spacing scale, or arbitrary one-off pixel values?
- **Color** — does color come from tokens, or are there hardcoded hex one-offs that drift from the palette? Are near-duplicate greys/brand shades multiplying?
- **Type** — are sizes/weights/line-heights from the scale, or ad-hoc? Too many type sizes doing the same job?
- **Borders & shadows** — one elevation language, or a mix of heavy shadows and borders applied at random?
- **Component variants** — same thing styled differently in different places (three button looks that should be one)?

### 2. Structure & hierarchy (is it designed, or just assembled?)
- **Boxes in boxes** — nested containers/cards each with their own border, background, and padding, stacking redundant chrome. Flatten: a bordered card inside a bordered panel inside a bordered section usually wants one container, not three.
- **Everything-is-a-card** — uniform gray boxes with no hierarchy; the layout reads as a grid of sameness with nothing leading the eye.
- **Weak hierarchy** — no clear primary action; headings, body, and metadata at similar weight; the important thing doesn't stand out.
- **Alignment & rhythm** — misaligned edges, inconsistent gutters, arbitrary vertical spacing that breaks the grid.
- **Density mismatch** — cramped where it should breathe, or airy where it should be dense, relative to the content and audience.

### 3. Craft & slop
- Default AI tells: purple gradients as filler, centered hero on dark mesh, three equal glass cards, glass on everything, emoji as section icons in serious UI.
- Decorative motion that doesn't aid comprehension; wrong easing (`ease-in` on enters); infinite loops.
- Fake depth, muddy contrast for "elegance," inconsistent iconography.

### 4. Accessibility (pass/fail — see `ux-principles`)
- Contrast (body ≥ 4.5:1, large/UI ≥ 3:1), visible focus states, hit-target sizes, meaning not by color alone, reduced-motion support.

## How to run it

1. Inventory the intended system via `detect-design-system` (what the tokens/scale/language *are*).
2. Walk the real UI — representative pages/components, and every meaningful state (empty, loading, error) — comparing usage against the intended system.
3. Reach into `impeccable` (audit/critique) and `emil-design-skills` (motion detail) for deeper, specialized passes when warranted.

## Output

A **prioritized findings list**, most impactful first. Each finding:
- **What** — the specific problem, with where it occurs.
- **Why it matters** — the effect on the user or the system's coherence.
- **Fix** — the concrete change (e.g. "unify to `--radius-md: 10px`; 4 components currently use 6/8/12px"; "remove the inner card border in `SettingsPanel` — collapse two nested containers into one").

Group fixes into quick wins vs. structural changes. Apply them in the **target project's repo**, honoring its existing system — an audit tightens a project's own identity, it never swaps in a different one. When a heuristic and the project's intentional style seem to conflict, flag it and confirm rather than "correcting" a deliberate choice.
