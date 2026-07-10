---
name: apply-color
description: Apply a project's existing color palette expressively across a website, instead of leaving it on buttons and links while everything else stays gray. Use when a design has a real palette but the pages feel flat, monochrome-by-accident, or under-colored; when styling a hero, a bento grid, a product shot, a set of categories, or a full section; or when someone says the brand colors "aren't being used." Five named techniques (gradient headings, color on a grid, color as a product background, color per category, one tint across a layout), each with its accessibility floor. Works strictly inside the project's OWN palette, never a house style, and never adds new colors.
---

# Apply Color Creatively

Most brands pick a full palette and then use a sliver of it. One accent lands on the buttons and the links, the headline is the same near-black as the body, every card is the same gray, and the other colors sit unused in a brand kit nobody opens. The palette is fine. The *application* is flat.

This skill is a small library of ways to put an existing palette to work across a page. It does not choose or expand the palette. If the project has no system yet, build one first (`build-design-system`); if it has one, these techniques express it harder without inventing a single new value.

**The one rule that outranks every technique below: use the project's own colors, and clear the accessibility floor every time.** Expressive color that fails contrast is not expressive, it is broken. Every technique here carries its own floor, and all of them defer to `ux-principles` and to the project's committed system (`honor-the-vibe` precedence).

## Before you reach for a technique

- **Honor the palette.** Pull from the project's committed tokens. If a technique seems to need a color the palette doesn't have, that is a signal to stop, not to add a hex. The point is to use what's there.
- **Pick one or two per page, not five.** These are seasoning. A hero gradient *and* a category-colored grid *and* a monochrome section *and* a tinted product shot on one screen is noise, and it buries the one thing the page is for. Choose the technique that serves this page's job, and let the rest of the page stay quiet so it reads.
- **Contrast is not optional.** Body text stays at 4.5:1, large text and UI at 3:1, against the actual surface it lands on, in every technique below. Check it on the real color, not an approximation.
- **Never let color carry meaning alone.** Any technique that uses color to say something (which one, what state, which category) needs a second signal: a label, an icon, a shape, or text. This is WCAG 1.4.1 and it is also just clearer.

## The techniques

### 1. Gradient on the heading

Run a gradient built from two or three palette colors across a large display heading, so the title itself carries the brand color instead of sitting in default near-black. Best on the biggest, boldest type on the page (a hero H1, a section opener), where the letterforms are heavy enough to hold a gradient without thinning out.

- **How.** `background: linear-gradient(...)` from palette stops, `background-clip: text`, transparent text fill. Keep the angle shallow and the stops adjacent on the palette so it reads as one brand move, not a rainbow.
- **Floor.** The gradient's *lightest* stop has to meet text contrast against the background, because the eye has to read every glyph, not just the dark end. Test the weakest point, not the average. Give it a solid-color fallback (`color:` set before the clip) for browsers and for when the clip fails. Keep it off long or small text, where a gradient hurts legibility and reads as decoration. One gradient heading per view is plenty.

### 2. Color on a grid

In a bento or card grid, give each cell a different fill drawn from the palette (one ink cell, one accent cell, one deep secondary, one photo) instead of the same gray card repeated. The variation gives the grid rhythm and lets color do the hierarchy: the most important cell gets the loudest fill.

- **How.** Assign fills from the palette per cell, and let the cell's text color flip to whatever meets contrast on that fill. Keep one cell quiet (a neutral or a photo) so the grid has somewhere to rest and the loud cells have something to play against.
- **Floor.** Every cell is its own contrast problem: the text and any icon inside each fill must clear the ratio on *that* fill, not on the page background. Stay inside the palette; four palette tints read as a system, four random colors read as a toy. Don't tint a cell purely to be colorful if it flattens the hierarchy you want.

### 3. Color as a product (or photo) background

Put a palette-color wash or gradient behind a product shot or a cutout subject, so the brand color frames the object instead of a flat white box. Turns a plain catalog image into something that belongs to the brand.

- **How.** A soft gradient from a palette color behind a transparent-background product image (or a subject cut out from its scene). Keep the wash tonal and let the product stay the hero; the color supports, it does not compete.
- **Floor.** Any text set over the wash meets contrast against the *darkest and lightest* part of the gradient it crosses. The product itself needs enough separation from the background not to disappear into a same-value wash. Reduced-motion and performance still apply if the background animates.

### 4. Color per category

Give each category, section, or principle its own color from the palette, used consistently as a wayfinding cue (four principles, four palette colors; three plans, three tints). Over a whole site, the color becomes a quiet map: readers learn "the copper things are pricing, the green things are support."

- **How.** Map one palette color to each category and apply it consistently everywhere that category appears (icon, tag, section accent, chart series). Consistency is the whole value; a color that means "pricing" here and "support" there means nothing.
- **Floor.** Color-coding must never be the only signal, so every category keeps its label and, ideally, a distinct icon or shape. That covers the reader who can't tell the two tints apart and the reader who lands mid-page with no legend. Keep the count small enough that the tints stay distinguishable; a dozen near-identical hues is a code nobody can read.

### 5. One tint across a layout

Build a whole section in a single color tone, one accent threading through a mostly monochrome zone (a dark section carried by one green signal, images tinted to the same tone, one colored button). The restraint makes the section feel deliberate and gives the page tonal rhythm between louder and quieter zones.

- **How.** Commit a section to one dominant tone and its neutrals, and let a single palette accent do all the pointing (the one link, the one active state, the one highlighted word). Tint the section's imagery toward the same tone so nothing breaks the mood.
- **Floor.** A monochrome zone is where contrast quietly slips, so hold body text at 4.5:1 and the accent at 3:1 against the section's own background, not the page's. Use this to create rhythm *between* sections; if every section is its own single tint, you're back to flat, just louder.

## Anti-slop

The failure mode is reaching past the project's palette for the default expressive gradient (AI purple, the same three-stop mesh on everything) instead of using the colors the brand actually owns. If the result would look at home on any other brand, it isn't applying *this* palette, it's applying the model's. Stop and go back to the project's tokens.

## Where this fits

- Run `honor-the-vibe` first; its precedence order still governs, and the project's own system wins over any technique here.
- Use `build-design-system` to establish the palette these techniques draw from, and `brand-kit` for the identity behind it.
- `ux-principles` sets the contrast and color-independence floor every technique above defers to.
- `design-audit` is the counterweight: it catches the same color used inconsistently, near-duplicate tints multiplying, and contrast failures, which is exactly how these techniques go wrong when overused.

---

*Technique set adapted from the "Apply Colors Creatively" breakdown by zachex, reframed here to work strictly inside a project's own palette and to carry its accessibility floor.*
