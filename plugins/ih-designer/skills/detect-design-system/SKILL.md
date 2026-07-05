---
name: detect-design-system
description: Inspect a codebase to discover its existing design system (if it has one) before making any visual change. Use whenever you start UI work in an unfamiliar project, are asked to add a component or page that must fit in, or are redesigning and need to know what to preserve. Inventories design tokens, theme files, Tailwind/CSS config, component libraries, fonts, color, spacing, radii, shadows, and motion, then produces a structured Design Read. Not for authoring a new system from scratch — for finding and honoring the one that's already there.
---

# Detect Design System

Find out what the project already is before you change it. A project with an existing design language is a set of commitments to honor, not a blank canvas. This skill produces the inventory that `honor-the-vibe` and every downstream decision depend on.

## How to inspect

Work outward from configuration to usage. Don't guess from a single file — triangulate.

### 1. Tokens and theme
Look for the source of truth for design values:
- CSS custom properties: `:root { --color-*, --space-*, --radius-*, --font-* }` in global CSS.
- Tailwind: `tailwind.config.{js,ts}` → `theme` / `theme.extend` (colors, fontFamily, spacing, borderRadius, boxShadow, screens). Also `@theme` blocks in Tailwind v4 CSS.
- Token files: `tokens.{json,ts}`, `design-tokens.*`, Style Dictionary, `theme.{ts,js}`, `*.css` with a variables layer.
- CSS-in-JS / styled-system: a `theme.ts`, `stitches.config`, `panda.config`, `vanilla-extract` theme, MUI `createTheme`, Chakra `extendTheme`.

### 2. Component library / framework
Identify what UI primitives exist so you extend rather than reinvent:
- Package signals in `package.json`: `shadcn`/`@radix-ui`, `@mui/*`, `@chakra-ui/*`, `antd`, `@mantine/*`, `@headlessui`, `daisyui`, `bootstrap`, `@shopify/polaris`, `@radix-ui/themes`, `tailwind-variants`, `cva`.
- A local `components/ui/` or `components/` directory — read 2–3 representative components to learn the house patterns (variant API, spacing habits, naming).
- CSS framework: Tailwind, vanilla CSS, CSS Modules, SCSS, or a utility layer.

### 3. Typography
- Font families and how they're loaded: `next/font`, `@font-face`, Google Fonts `<link>`, Fontsource, self-hosted `.woff2`.
- The type scale actually in use (heading sizes, body size, line-heights, tracking) and pairing (display vs. text, serif vs. sans, mono usage).

### 4. Color
- The real palette: brand/primary, neutrals/greys, semantic (success/warn/error/info), surface/background/ink.
- Color space in use (hex, HSL, OKLCH) and whether there's a ramp/scale.
- Dark mode: is it supported, and how (class strategy, `data-theme`, `prefers-color-scheme`, separate token sets)?

### 5. Space, shape, elevation
- Spacing scale (4px base? 8px? bespoke?) and density (tight vs. airy).
- Radius language (sharp 0, subtle 4–6px, soft 12–16px, pill).
- Elevation: borders vs. shadows, shadow softness, layering conventions.

### 6. Motion
- Transition/animation conventions: durations, easings (is `ease-out` used for enters?), libraries (`framer-motion`/`motion`, `@react-spring`, CSS keyframes, GSAP).
- How restrained or expressive the existing motion is.

### 7. Voice and content
- UX writing tone in existing copy (terse/formal/playful), casing conventions (Title Case vs. sentence case), microcopy patterns.

## Output: the Design Read

Summarize findings as a compact, structured read — not prose. Example shape:

```
DESIGN READ — <project>
System:      Tailwind v4 + shadcn/ui (Radix primitives), tokens in app/globals.css @theme
Maturity:    Established — cohesive tokens, ~20 UI components, consistent usage
Type:        Geist Sans (text) + Geist Mono (code); scale 14/16/20/24/32/48, tight tracking on display
Color:       OKLCH ramp; brand ~oklch(0.55 0.2 265), neutral zinc ramp; semantic set present
Dark mode:   Yes — .dark class strategy, full token parity
Space:       4px base, generally airy; section rhythm 96–128px
Shape:       Radius 8px default, 12px cards; borders over shadows, shadows very soft
Motion:      Restrained — 150–200ms ease-out enters, framer-motion for layout only
Voice:       Sentence case, terse, confident, no emoji
Vibe:        Linear-adjacent: quiet, precise, developer-facing, high-craft minimal
GAPS:        No empty-state or error-state patterns; toast styling ad hoc
```

Add a **maturity verdict**, because it changes strategy:
- **Established** — cohesive tokens and consistent usage. Preserve rigorously; match, don't invent.
- **Partial** — some tokens, inconsistent usage, drift. Consolidate toward the strongest existing direction.
- **None** — inline styles, ad-hoc values, no shared vocabulary. Here it's appropriate to establish the project its own system — use `build-design-system` (and `brand-kit` for identity). Never hand it a generic or reused one.

## Then hand off

- Feed the Design Read back into `honor-the-vibe` to set the precedence and the plan.
- **Established** → the existing system wins; extend it invisibly, and use `design-audit` to check it's applied consistently.
- **Partial** → consolidate toward the strongest existing direction with `build-design-system`, then `design-audit`.
- **None** → build the project its own with `build-design-system`, anchored to its goals and brand — never to a default.

Whatever you produce is integrated into the target project's repo, not designer's. Never propose a restyle of an Established system unless the user explicitly asked for a redesign — fitting in is the job.
