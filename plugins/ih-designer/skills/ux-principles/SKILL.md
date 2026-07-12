---
name: ux-principles
description: Foundational UX and usability principles that hold across any aesthetic — hierarchy, accessibility, cognitive load, interaction design, forms, states, and UX writing. Use when designing or reviewing any interface to check the non-negotiable minimums (contrast, focus, hit targets, feedback, error recovery) and to make hierarchy and flow decisions. These principles constrain quality; they never dictate a specific style. Load the companion ux-principles.md for the full checklist.
---

# UX Principles

The craft floor. These hold no matter the vibe — a brutalist page and a trust-first service both owe the user legible hierarchy, real focus states, forgiving errors, and honest feedback. Principles here **constrain** style; they don't pick one. Honoring a project's vibe never means shipping something unusable.

Read **`ux-principles.md`** (in this skill's directory) for the full, itemized checklist. Use this SKILL.md as the working summary and the reviewer's lens.

## The non-negotiables

Fail any of these and the design is broken regardless of how it looks:
- **Contrast** — body text ≥ 4.5:1, large text ≥ 3:1, UI/graphic boundaries ≥ 3:1. Muted grey on tinted near-white is the most common failure.
- **Focus** — every interactive element has a visible, non-color-only focus state. Keyboard reaches everything in a sensible order.
- **Hit targets** — ≥ 24px (WCAG 2.2), ≥ 44px for touch-primary UI.
- **Feedback** — every action gets an immediate, legible response: loading, success, error, empty.
- **Error recovery** — errors are preventable, specific, and recoverable. Never a dead end, never "something went wrong."
- **Don't rely on color alone** to carry meaning (state, required fields, chart series).
- **Respect `prefers-reduced-motion`** — motion is enhancement, not a gate.

## The working principles

1. **Hierarchy first.** One clear primary action per view. Size, weight, spacing, and color express importance. If everything shouts, nothing is heard.
2. **Reduce cognitive load.** Recognition over recall. Sensible defaults. Progressive disclosure. Chunk complexity; don't dump it.
3. **Consistency.** Same thing looks and behaves the same everywhere. Match the project's existing patterns (see `detect-design-system`) before inventing.
4. **Design the states, not just the happy path.** Every screen owes four — loading, success, error, empty — plus partial, too-much-data, offline, first-run where they apply. Skeletons that mirror the layout for whole screens and content regions (prime the user before the data lands); a loader for smaller parts where a skeleton makes no sense. Match the feedback surface to the stakes: toasts for transient low-stakes status, never for important errors (put those inline or in a persistent banner); modals only for the rare thing the user must acknowledge or decide, since they take over the screen. These are where real products live or die.
5. **Forms are where users struggle.** Label clearly, group logically, validate inline and kindly, preserve input on error, ask for the minimum.
6. **Flow over screens.** Design the sequence, not isolated views. Minimize steps to the goal; keep the user oriented (where am I, what's next).
7. **Content is the interface.** Clear, concrete UX copy in the project's voice beats clever. Sentence case reads faster. Every button says exactly what happens when pressed — the label is a promise, never "OK"/"Submit".
8. **Accessibility is baseline, not a feature.** Semantic HTML, labels, landmarks, alt text, ARIA only when semantics fall short.
9. **Performance is UX.** Perceived speed, skeleton/optimistic states, no layout shift, fast to interactive.
10. **Respect the user's attention and trust.** No dark patterns, no manufactured urgency, no interruption without cause.

## Using this in a review

Go non-negotiables first (these are pass/fail), then walk the working principles against the actual flows and states. Report concrete failures with the fix, not vague notes. Tie every call back to the user's goal and the project's vibe — a fix that damages the project's identity to satisfy a heuristic is the wrong fix; find one that does both.
