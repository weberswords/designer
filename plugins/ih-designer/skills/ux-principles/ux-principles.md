# UX Principles — Full Checklist

The itemized reference behind the `ux-principles` skill. Style-agnostic craft standards: they hold under any aesthetic and constrain quality without dictating a look. Use as a design checklist and as a review rubric.

---

## 0. The non-negotiables (pass/fail)

If any of these fail, the design is broken regardless of how good it looks.

- [ ] **Text contrast** — normal text ≥ 4.5:1, large text (≥ 24px, or ≥ 18.66px bold) ≥ 3:1.
- [ ] **Non-text contrast** — UI component boundaries, icons, focus indicators, and meaningful graphics ≥ 3:1 against adjacent colors.
- [ ] **Visible focus** — every interactive element shows a clear focus indicator that does not rely on color alone.
- [ ] **Full keyboard operability** — everything reachable and operable by keyboard, in a logical order, with no traps.
- [ ] **Hit target size** — ≥ 24×24px minimum (WCAG 2.2); ≥ 44×44px for touch-first interfaces.
- [ ] **Action feedback** — every user action produces immediate, perceivable feedback (state change, loading, confirmation).
- [ ] **Error recovery** — errors are specific, human, and recoverable; input is preserved; no dead ends.
- [ ] **Meaning not by color alone** — state, required fields, validity, and data series are also carried by text, icon, or shape.
- [ ] **Reduced motion** — `prefers-reduced-motion` is respected; no essential information conveyed only through motion.
- [ ] **Semantic structure** — real headings, landmarks, lists, and labels; one `<h1>`; logical heading order.

---

## 1. Visual hierarchy

- One clear primary action per view; secondary and tertiary actions are visibly subordinate.
- Importance is expressed through size, weight, spacing, and color contrast — in that rough order of strength.
- Group related things (proximity); separate unrelated things (whitespace). Whitespace is structure, not leftover.
- Alignment is deliberate and consistent; establish a grid and hold it.
- Scan pattern matches reading order and the user's goal (F-pattern for text, Z-pattern for simple marketing).
- If everything is bold/large/colored, nothing reads as important. Contrast requires restraint elsewhere.

## 2. Cognitive load

- Prefer recognition over recall — show options rather than requiring memory.
- Provide sensible defaults; the best form field is one already filled correctly.
- Progressive disclosure: reveal complexity as needed, not all at once.
- Chunk information (Miller's ~7±2); group long lists and forms into labeled sections.
- Reduce choices at each decision point; too many options paralyzes (Hick's Law).
- Leverage existing conventions and mental models — don't make users relearn basics.

## 3. Consistency

- Internal: the same element looks and behaves the same everywhere in the product.
- External: honor platform and web conventions (link affordances, control behaviors, iconography).
- Match the project's own established patterns first (run `detect-design-system`); consistency with the house beats personal preference.
- Consistent language: one term per concept; don't call it "profile" here and "account" there.

## 4. Feedback and system status

- Always show system state: idle, loading, success, error, empty, disabled.
- Response times: < 100ms feels instant; < 1s keep attention with a subtle indicator; > 1s show progress; > 10s show progress + allow other work.
- Optimistic UI where safe; skeletons over spinners for content; never a blank flash.
- Confirm consequential and destructive actions; make destructive actions undoable where possible (undo beats confirm).

## 5. States — design all of them

Never ship only the happy path. For every meaningful surface, design:

- **Empty** — first-run and zero-data; guide the next action, don't just say "no items."
- **Loading** — skeleton or progress that matches final layout; avoid layout shift.
- **Partial** — some content, some pending; streamed/paginated data.
- **Error** — specific cause, clear recovery, preserved context.
- **Success** — confirmation proportional to the action.
- **Too much** — long lists, overflow, truncation, pagination/virtualization.
- **Edge** — long strings, missing images, extreme numbers, i18n length, RTL.
- **Offline / degraded** — where relevant.

## 6. Forms

- Labels always visible (not placeholder-as-label); placeholders show format, not meaning.
- Group and order fields logically; one column beats two for linear flows.
- Ask for the minimum; defer optional fields; explain why anything sensitive is needed.
- Validate inline and forgivingly; show errors next to the field, in plain language, with how to fix.
- Preserve all input on error — never wipe a form.
- Right input for the data (native date/number/select, correct `inputmode`, autocomplete tokens).
- Clear required/optional convention; disable or clearly gate submit; show submit progress.

## 7. Navigation and flow

- Users always know: where am I, what can I do, how do I get back.
- Minimize steps to the goal; remove, merge, or defer steps before styling them.
- Keep the user oriented across multi-step flows (progress, breadcrumbs, clear back).
- Make the default path the easy path; don't hide the primary journey behind chrome.
- Preserve context on navigation (scroll, filters, unsaved work warnings).

## 8. Content and UX writing

- Clear beats clever; concrete beats abstract. Say what happens.
- Sentence case for UI text (reads faster, feels human); reserve Title Case for proper nouns/brands.
- Buttons name their action ("Save changes", "Delete project"), not "OK"/"Submit".
- Error messages: what happened, why, what to do next — no blame, no jargon, no "oops".
- Match the project's voice (see `brand-kit`); tone is part of the vibe.
- Front-load the important word; cut filler; prefer active voice.

## 9. Accessibility (beyond the non-negotiables)

- Semantic HTML first; ARIA only to fill genuine gaps, never as a substitute for semantics.
- Label every control (visible label, `aria-label`, or `aria-labelledby`); associate labels with inputs.
- Meaningful alt text; empty `alt=""` for decorative images.
- Respect user settings: reduced motion, reduced transparency, forced colors / high contrast, font scaling (support 200% zoom without loss).
- Announce dynamic changes (live regions) for async updates and toasts.
- Test with keyboard only and with a screen reader on critical flows.

## 10. Performance as UX

- Perceived performance matters as much as raw speed — respond instantly, load progressively.
- No cumulative layout shift; reserve space for images, embeds, and async content.
- Fast to interactive; defer non-critical work; lazy-load below the fold.
- Optimize the critical rendering path; images sized and modern-format; fonts with sensible fallbacks and `font-display`.

## 11. Trust and ethics

- No dark patterns: no forced continuity, roach motels, confirmshaming, disguised ads, or bait-and-switch.
- No manufactured scarcity or fake urgency.
- Ask for consent honestly; make opt-out as easy as opt-in.
- Respect attention: interrupt only with cause; make notifications controllable.
- Be honest about state, cost, and consequence before the user commits.

---

## Review rubric (quick pass)

1. Run the **non-negotiables** — any fail is a blocker.
2. Walk each real **flow** and each **state** (§5) — not just the default screen.
3. Check **hierarchy** (§1) and **cognitive load** (§2) against the user's actual goal.
4. Check **forms** (§6) and **content** (§8) where present.
5. Report concrete failures with the specific fix. Every fix must also honor the project's vibe — if a heuristic and the identity collide, find the option that satisfies both.
