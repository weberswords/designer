# IHDS — Default Tokens

The Intelligent Hoodlums default token set. A **fallback starting point** for blank-slate projects, not a template to stamp everywhere. Adapt every value toward the project's Design Read; a project's own tokens always override these.

> **Set your real brand values once.** Everything marked `TODO` is a neutral placeholder. Replace the brand color and type families with the studio's actual brand, then let per-project brand kits override as needed. Neutrals, spacing, radius, and motion below are sensible defaults you can usually keep.

Values use **OKLCH** for perceptual consistency and easy ramp generation. Ship them however the project's stack expects (CSS custom properties, `@theme`, Tailwind config, a token file).

---

## Color

### Brand
```
--brand:        TODO  /* studio brand color — e.g. oklch(0.62 0.19 265). Verify contrast on --surface and as text. */
--brand-ink:    TODO  /* readable text color for on-brand surfaces — ≥4.5:1 on --brand */
--accent:       TODO  /* optional single accent for highlights; use sparingly */
```

### Neutrals (default: cool-neutral ramp — keepable)
```
--bg:           oklch(0.99 0.002 260)   /* page background (light) */
--surface:      oklch(0.97 0.003 260)   /* cards, panels */
--surface-2:    oklch(0.94 0.004 260)   /* raised / hover */
--border:       oklch(0.90 0.005 260)   /* hairlines, dividers */
--ink:          oklch(0.22 0.01 260)    /* body text — ~13:1 on --bg */
--ink-muted:    oklch(0.45 0.01 260)    /* secondary text — verify ≥4.5:1 on --bg */
--ink-subtle:   oklch(0.60 0.01 260)    /* tertiary / placeholder — large text or non-essential only */
```

### Semantic
```
--success:      oklch(0.60 0.15 150)
--warning:      oklch(0.75 0.15 80)
--error:        oklch(0.58 0.20 25)
--info:         oklch(0.62 0.14 250)
```

### Dark mode (invert lightness, hold hue/chroma; parity required)
```
--bg:           oklch(0.17 0.005 260)
--surface:      oklch(0.21 0.006 260)
--surface-2:    oklch(0.25 0.007 260)
--border:       oklch(0.30 0.008 260)
--ink:          oklch(0.95 0.006 260)
--ink-muted:    oklch(0.72 0.008 260)   /* verify ≥4.5:1 on dark --bg */
--ink-subtle:   oklch(0.58 0.008 260)
/* brand/semantic: nudge lightness up slightly for dark surfaces; re-verify contrast */
```

> **Contrast rule:** body text ≥ 4.5:1, large/UI ≥ 3:1, on the actual surface it sits on. Re-check `--ink-muted` and `--brand`-as-text in both themes before shipping.

---

## Typography
```
--font-display:  TODO   /* headings — set to the studio's display family + fallbacks */
--font-text:     TODO   /* body — set to the studio's text family + fallbacks */
--font-mono:     ui-monospace, "SF Mono", "JetBrains Mono", Menlo, monospace
```

### Scale (major-third-ish, tuned for UI; adjust density to the project)
```
--text-xs:   0.75rem   /* 12 */
--text-sm:   0.875rem  /* 14 */
--text-base: 1rem      /* 16 — body default */
--text-lg:   1.25rem   /* 20 */
--text-xl:   1.5rem    /* 24 */
--text-2xl:  2rem      /* 32 */
--text-3xl:  3rem      /* 48 */
--text-4xl:  4rem      /* 64 — display */
```
- Line-height: ~1.5 for body, ~1.1–1.2 for display.
- Tracking: slightly negative on large display; default on body.
- Weights: 400 body, 500 medium UI, 600–700 headings. Set what's actually licensed/loaded.

---

## Space (4px base — keepable)
```
--space-1: 0.25rem   /* 4  */
--space-2: 0.5rem    /* 8  */
--space-3: 0.75rem   /* 12 */
--space-4: 1rem      /* 16 */
--space-6: 1.5rem    /* 24 */
--space-8: 2rem      /* 32 */
--space-12: 3rem     /* 48 */
--space-16: 4rem     /* 64 */
--space-24: 6rem     /* 96 — section rhythm */
```
Default density: airy. For dense/data-heavy product UI, drop to a tighter rhythm.

## Radius (default: subtle-soft)
```
--radius-sm:  0.375rem  /* 6  — inputs, chips */
--radius-md:  0.625rem  /* 10 — buttons, cards */
--radius-lg:  1rem      /* 16 — modals, large surfaces */
--radius-full: 9999px
```
Shift toward `0` for a sharp/brutalist read, or larger for a soft/friendly one — per the Design Read.

## Elevation (borders first, shadows soft)
```
--shadow-sm:  0 1px 2px oklch(0.2 0.01 260 / 0.06);
--shadow-md:  0 2px 8px oklch(0.2 0.01 260 / 0.08);
--shadow-lg:  0 8px 30px oklch(0.2 0.01 260 / 0.12);
```
Prefer `--border` + `--shadow-sm` over heavy shadows. In dark mode, lean on surface-lightness steps more than shadow.

## Motion (honest, fast, restrained)
```
--ease-out:   cubic-bezier(0.16, 1, 0.3, 1);   /* enters */
--ease-in:    cubic-bezier(0.7, 0, 0.84, 0);   /* exits */
--ease-inout: cubic-bezier(0.65, 0, 0.35, 1);  /* moves */
--dur-fast:   150ms;   /* hovers, small UI */
--dur-base:   220ms;   /* enters, popovers */
--dur-slow:   400ms;   /* larger transitions — use sparingly */
```
- Enter with `--ease-out`, exit with `--ease-in`. Never `ease-in` for an enter.
- Prefer transform/opacity; avoid animating layout-triggering properties.
- Always gate non-essential motion behind `@media (prefers-reduced-motion: no-preference)`.

---

## Applying
- Emit these into the project's native token layer; don't fight its stack.
- Change `--brand`, `--font-*`, density, radius, and motion to fit the Design Read — that's the point.
- Keep the craft invariants: contrast, spacing rhythm, motion easing, accessibility.
- A project's own values, or its brand kit, override anything here.
