---
name: brand-kit
description: Capture, define, and apply a project's brand kit — logo, color, typography, voice, imagery, and motion personality — so design work stays on-brand and identity is preserved. Use when a project has brand assets that must be honored, when starting a project that needs a brand foundation defined, or before a redesign (existing brand is starting material, not optional). Produces or reads a brand-kit.md the whole team and toolkit can work from, integrated into the target project's repo. designer has no house brand of its own — this captures each project's own identity.
---

# Brand Kit

A brand kit is a project's identity, captured so every decision honors it. This skill does two jobs: **extract** an existing brand into a usable kit, or **establish** one when a project has none. Either way the output is a `brand-kit.md` that anchors color, type, voice, and feel — the raw material `honor-the-vibe` uses to keep a project looking like *itself*.

Use the companion **`brand-kit-template.md`** in this directory as the structure to fill in.

## When there's an existing brand — extract and honor

Most projects already have identity, even if scattered. Your job is to find and formalize it, not replace it.

1. **Gather the evidence.** Logo files, favicon, existing site/app, marketing, `detect-design-system` output, README, social profiles, pitch decks, existing CSS/tokens.
2. **Pull the primitives.** Read exact values, don't approximate:
   - **Logo** — variants (full/mark/wordmark), clear space, min size, do's and don'ts, on-light vs. on-dark.
   - **Color** — brand/primary, secondary, neutrals, semantic; exact values and preferred color space (prefer OKLCH for new ramps). Note where each is allowed.
   - **Type** — display and text families, weights licensed/loaded, the scale, pairing rules, fallbacks.
   - **Imagery** — photography vs. illustration, treatment (duotone, grain, flat), iconography style, do's and don'ts.
   - **Voice** — three adjectives, casing, person (we/you), humor level, words to use and avoid. Capture *who* is speaking, not just how: a real person or team behind the brand, and how much of them the copy is allowed to show. A brand with a human in it is harder to forget and harder to copy — expose the maker rather than laundering the personality into faceless corporate.
   - **Motion personality** — snappy vs. gentle, expressive vs. restrained, signature transitions.
3. **Name the vibe in one line.** e.g. *"Warm editorial confidence — serif display, cream paper, ink, one hot accent; unhurried, human, never corporate."*
4. **Write it to `brand-kit.md`.** Fill the template. Flag genuine gaps (e.g. no dark-mode brand color) rather than inventing — propose, mark as proposed, get confirmation.

## When there's no brand — establish one

Only when the project genuinely has no identity (confirm via `detect-design-system`). Anchor everything to the project's **goal and audience**, never to a default aesthetic.

1. Start from the Design Read: kind, audience, goals, vibe words.
2. Choose a direction that fits *this* project — reach into `taste-skill` and `impeccable` for taste and craft, and pair with `build-design-system` to turn the identity into real tokens in the project's repo.
3. Define the minimum viable kit: one brand color + neutral ramp, one type pairing, a voice in three words, a motion stance. Ship a coherent little system, not a 40-page guide.
4. Verify accessibility on the brand palette immediately (contrast on real surfaces) — a beautiful brand color that fails on text is not usable.
5. Write it to `brand-kit.md` and treat it as living.

## Applying the kit

- The brand kit sits just under the project's own design system in the precedence order (see `honor-the-vibe`). Where the design system encodes brand values as tokens, the tokens win at the code level and the kit explains the *why*.
- Every surface should be traceable to the kit: this color because brand primary, this type because display family, this tone because the voice is "warm, precise, human."
- Keep brands distinct. Do not let one project's kit bleed into another. If two projects start looking alike, the kit isn't being honored.

## Output contract

A single `brand-kit.md` at the project root (or `docs/brand-kit.md`) following the template: overview + one-line vibe, logo, color (with exact values + contrast notes), typography, imagery/icons, voice, motion, and a short do/don't list. Concrete values, not adjectives alone.
