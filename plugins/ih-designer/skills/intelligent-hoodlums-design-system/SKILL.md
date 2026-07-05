---
name: intelligent-hoodlums-design-system
description: The Intelligent Hoodlums house design system — the studio's craft baseline, default tokens, and design philosophy. Use as a FALLBACK when a project has no identity of its own (confirmed via detect-design-system), or as a source of craft standards and sensible defaults that never override a project's existing system or brand. This is the studio's taste, not a template to stamp on every project. When a project has its own vibe, that vibe wins.
---

# Intelligent Hoodlums Design System (IHDS)

The studio's house system: how The Intelligent Hoodlums build interfaces when starting from nothing, and the craft standards that hold across everything the studio ships. Read `philosophy.md` for the studio's stance and `design-tokens.md` for the default token set.

## Read this first: IHDS is a floor and a fallback, never a stamp

The prime directive of this whole toolkit is to **honor each project's own vibe** (see `honor-the-vibe`). IHDS does not compete with that — it sits at the *bottom* of the precedence order:

1. Project's own design system → wins
2. Project's brand kit → wins
3. Craft references (impeccable, emil, taste) → raise quality
4. Universal UX principles → constrain
5. **IHDS → only when there's nothing above it, or as craft standards that never override the above**

So use IHDS in exactly two ways:
- **As a starting point** for a genuinely blank project (no system, no brand — confirm with `detect-design-system`). Even then, immediately steer it toward *the project's* goals and audience; don't ship the studio's personality onto someone else's product.
- **As craft standards** — the non-style parts (contrast discipline, spacing rhythm, motion honesty, accessibility floor) apply everywhere because they're quality, not identity.

If you ever find yourself importing IHDS *colors, type, or personality* into a project that already has its own, stop. That's homogenization — the exact failure this system is built to prevent.

## The studio's craft standards (apply everywhere)

These are quality, not taste — they hold under any aesthetic:
- **Contrast is non-negotiable.** Body ≥ 4.5:1, large/UI ≥ 3:1. No muted grey on tinted white.
- **Commit to choices.** Real tokens, real code, no hedged half-generic output.
- **Space with intent.** Consistent spacing scale; whitespace is structure. Rhythm over randomness.
- **Type does the heavy lifting.** A confident type system carries most of the design; get the scale and hierarchy right before decorating.
- **Motion is honest.** `ease-out` for enters, `ease-in` for exits, fast (150–250ms) for UI. Motion serves comprehension, not decoration. Respect `prefers-reduced-motion`.
- **Elevation with restraint.** Prefer borders and very soft shadows over heavy drop shadows.
- **Accessibility is baseline.** Semantic HTML, focus states, keyboard paths, labels — always.
- **No slop.** No default AI-purple gradients, no centered-hero-on-dark-mesh reflex, no glass on everything.

## The default aesthetic (fallback only)

When IHDS *is* the starting point, its default character is: **quiet confidence, high craft, content-first.** Restrained by default so the project's own personality has room to emerge — not a loud house style that fights whatever the project becomes. Neutral-forward palette, one committed brand color, a strong type pairing, generous space, minimal motion. Then push it toward the project.

See `design-tokens.md` for the concrete default token set. **The brand-color and typography values there are placeholders marked `TODO` — set them to the studio's real brand once, and per-project override always wins.**

## How to use it

1. Confirm the project is a blank slate (`detect-design-system` → maturity: None).
2. Pull the Design Read (`honor-the-vibe`) — kind, audience, goals, vibe.
3. Start from `design-tokens.md`, then **adapt** toward the read. Change the brand color, type, density, and motion to fit the project. Keep the craft standards.
4. If the project is a redesign or has any brand assets, use `brand-kit` first — IHDS defers to it.
5. Verify contrast and states before you call it done.
