---
name: brand-kit
description: Capture, define, and apply a project's brand kit — logo, color, typography, voice, imagery, and motion personality — so design work stays on-brand and identity is preserved. Use when a project has brand assets that must be honored, when starting a project that needs a brand foundation defined, or before a redesign (existing brand is starting material, not optional). Also use when someone asks to be interviewed for a brand kit or brand guide; interview mode asks one question at a time and writes brand-kit.md from the answers. Produces or reads a brand-kit.md the whole team and toolkit can work from, integrated into the target project's repo. designer has no house brand of its own — this captures each project's own identity.
---

# Brand Kit

A brand kit is a project's identity, captured so every decision honors it. This skill does three jobs: **interview** someone to build a kit from their answers, **extract** an existing brand into a usable kit, or **establish** one when a project has none. In each case the output is a `brand-kit.md` that anchors color, type, voice, and feel — the raw material `honor-the-vibe` uses to keep a project looking like *itself*.

Use the companion **`brand-kit-template.md`** in this directory as the structure to fill in.

## Interview mode: build the kit from answers

Use this when someone asks you to interview them for a brand kit or brand guide. It's the same interview as the brand guide prompt on [studiowlabs.com/ai-guidelines](https://studiowlabs.com/ai-guidelines), run inside the project, so you can read what's already there.

Ask one question at a time, and wait for the answer before you ask the next. Give two or three short examples with each question, so the person has something to react to. If the project already answers a question, show what you found and ask them to confirm it.

Work through these in order.

1. Ask what the product does, in one sentence. For example, "It books dog grooming appointments" or "It tracks reading for a classroom."
2. Ask who it's for. For example, busy pet owners, third-grade teachers, or the staff of a small nonprofit.
3. Ask for three words that describe how it should feel. For example, calm, playful, and trustworthy.
4. Ask what they already have, like a logo, colors, fonts, or a site. Before you ask, look in the repo for logo files, CSS variables or tokens, and font imports, and run `detect-design-system` if it hasn't run yet. Anything that exists is starting material, so honor it before you suggest anything new.
5. Only then suggest colors. Propose a primary, a background, a surface, a text color, and a muted text color, and explain why each one fits what they told you. Ask them to keep, change, or replace each one.
6. Check every text and background pair: text on the background, muted text on the background, button text on the primary, and the primary on the background. Give each pair's contrast ratio and say what it's OK for. Body text needs at least 4.5 to 1. Large text (24 px, or about 19 px bold) and the edges of buttons and form fields need at least 3 to 1. Flag any pair under 4.5 to 1 for body text, and offer a darker or lighter version of the same color that passes. List any pair under 3 to 1 as one to never use.
7. Ask which fonts headings and body text should use. Offer two or three pairings that fit their three words, and keep body text at 16 px or larger.
8. Ask for two or three things they've written themselves, like an email to a customer, a post, or an About page. Describe the voice from those samples, then ask which phrases they use and which they never use. Write one sentence in that voice and ask whether it sounds like them. If they have no samples, leave the voice marked `(proposed)`. Don't invent one.
9. Last, ask about the optional pieces: where the logo files live and how much space to keep around the logo, the style of images and icons, and whether anything on screen should move.

While you interview, don't make up facts about their business. If you don't know something, ask, or leave it blank. Compute each contrast ratio with the WCAG relative luminance formula, and run a short script if you can, since ai tools get this math wrong when they estimate. Tell the person to check every ratio in [WebAIM's Contrast Checker](https://webaim.org/resources/contrastchecker/) before they rely on the kit.

When the interview is done, write `brand-kit.md` from `brand-kit-template.md`. Put the product, audience, and three words in the overview, the colors and every measured pair in the color section, the fonts in typography, and the voice from their samples in the voice section. Mark anything they didn't confirm as `(proposed)`, and mark any section you didn't cover as a gap. Show them the file and ask what they'd change.

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
