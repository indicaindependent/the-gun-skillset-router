# DESIGN PRINCIPLES

Every rule here came out of a research pass, and several of them condemned work
that already existed. They are recorded with their reasoning so they can be
argued with rather than merely obeyed.

---

## 1. THE RENDERING CHOICE IS THE ACCESSIBILITY CHOICE

This is the least obvious principle and the most consequential.

A canvas element paints pixels. It puts **nothing** in the document, so assistive
technology receives nothing, and it rasterises when magnified. That makes the most
popular charting approach the *wrong* default for a low-vision reader, despite
being the obvious pick.

Preference order:

| Rank | Approach | Why |
| ---: | :--- | :--- |
| 1 | CSS and DOM elements | Perfect reflow at 400% zoom, fully in the document |
| 2 | Inline SVG | Vector-clean under magnification, real text nodes |
| 3 | Canvas | Avoid. Rasterises, and is invisible to assistive tech |

Every asset in this repository is inline SVG with real `<text>` nodes, a `role`,
a `<title>` and a `<desc>`. PNG exports exist only as previews — the vector is the
deliverable.

**Corollary: every chart owes a real data table.** A visual is an accelerator for
someone who can use it, never the sole channel for the information.

---

## 2. TEXT ALWAYS SITS ON A SOLID SURFACE

A saturated gradient behind text drops contrast below any usable floor, and the
exact ratio varies by position, so it cannot even be measured honestly.

Once text sits on a **known solid card**, its contrast is *provable* rather than
situational. That single structural change is what allows a contrast table to
exist at all.

This is also why **no asset here has a transparent background.** A transparent SVG
inherits whatever colour the host page happens to use — light theme, dark theme,
someone's custom stylesheet — and its text contrast becomes unprovable the moment
it leaves its origin. Every asset paints its own background first.

---

## 3. NO GLOW, NO SCANLINES, NO CHROMATIC ABERRATION

These were removed from an existing visual identity, not merely avoided.

| Effect | Why it is gone |
| :--- | :--- |
| Glow on type | Destroys the solid edge that contrast measurement assumes |
| Scanlines | Visual fatigue, reduced edge sharpness, photosensitivity hazard |
| Chromatic aberration | Same, plus it makes small type genuinely unreadable |
| Animation and pulsing | Seizure risk, and motion blurs the edges being measured |

**The look survives without them.** Solid regular and bold letterforms, corner
brackets, hairline rules, monospace tracking, and one accent colour doing a real
job as a focus indicator. Texture comes from *structure*, not from effects.

The original identity failed all three of these tests. Keeping the aesthetic
meant identifying which parts carried the feeling and which parts were merely
hazard.

---

## 4. ONE DATA SERIES IS ONE COLOUR

Every bar in the ledger chart is the same teal.

Giving each bar its own hue encodes **nothing** the label does not already state,
and it is the single fastest way to make a serious chart look like a toy. Colour
is reserved for genuine categorical distinction — the chamber diagram uses seven
hues because there are seven real discipline groups.

Related rules from the same research:

- **Every mark carries a stroke**, so contrast holds regardless of fill.
- **A severity ramp must invert by colour scheme.** A light-to-dark scale
  collapses on a dark background.
- **Aggregate co-located points** rather than overplotting them.
- **Never draw a basemap you cannot verify.**

---

## 5. THE DIAGRAM CARRIES ITS OWN LABELS

A chart whose legend lives only in the surrounding caption fails anyone who zooms
into the image, saves it, or views it out of context.

The chamber index sits **inside** the hero image. All twenty-four are named there,
at 14px minimum, on a solid background.

Minimum type size across every asset is **12px at natural scale**, and the
generator refuses to write a file that goes below it.

---

## 6. NO EMOJI, ANYWHERE

Not as marks, not as row icons, not as decoration.

An emoji is a font-dependent glyph that renders differently on every platform,
carries no reliable semantic, and reads as unserious in technical work. Real
vector marks, numerals, and clean typography do the job properly.

A mark must also survive **monochrome and extreme downscale**. If it only works
in full colour at full size, it is an illustration, not an identity.

---

## 7. VERIFY THE ASSET, NOT THE INTENTION

Three of the five diagrams in this repository failed their own rules on first
generation, and every failure looked completely finished.

| Defect | Consequence | How it was caught |
| :--- | :--- | :--- |
| Legend overflowed the canvas by 148px | Nine labels cut off; one entire discipline group vanished | Comparing text coordinates against the viewBox |
| Letter-spacing passed into the text-anchor slot | Invalid SVG; both the anchor and the tracking silently dropped | Enumerating every anchor value present in the output |
| Two item-counting bugs | The findings total was wrong in two directions | Two independent parsers disagreeing, then tracing the exact gap |

The generator now **refuses to write** an asset that overflows its canvas, uses an
invalid anchor value, carries a blur filter, or drops type below 12px. That guard
was itself tested by feeding it a deliberately broken diagram to confirm it says
no.

This is the principle the rest depend on: **a thing that looks finished is not the
same as a thing that was checked.** Contrast ratios here are computed from hex
values. Type sizes are parsed from the output. Overflow is measured against the
canvas. None of it is asserted.

---

## 8. PUBLISHING IS A SECURITY DECISION

Before anything went into this repository it was scanned — for credential-shaped
strings, for infrastructure identifiers, for personal names, for absolute
filesystem paths, and for code that had no business shipping in a design
repository.

That scan removed a generator script, a compiled cache directory, a peer system's
name, and an operator's first name. All of it was caught **before** publication,
which is the only time catching it is cheap.

The owner labels in the ledger diagram are generic — `SELF`, `PEER AGENT`,
`OPERATOR` — and that turned out to be a design improvement as well as a security
one. The anonymised version teaches the pattern instead of documenting one
person's private estate.
