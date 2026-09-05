# THE GUN

### A 24-chamber expert routing system, drawn rather than described

This repository is a **visual showcase**. No code, no build, nothing to install —
just the design of a routing architecture and the vector assets that explain it.

---

## THIS IS WHERE THE THESIS STARTED

**Created 2026-08-21** — the earliest repository in the
**[ka-tet](https://github.com/indicaindependent/ka-tet)**, and the origin of everything in it.
Verifiable rather than claimed: the seats that grew out of this design were created two days to
two weeks later.

    2026-08-21   the-gun-skillset-router   this repository, the design
    2026-08-23   the-gunslinger            first seat built from it
    2026-09-03   ka-tet                    the hub, once there was more than one seat
    2026-09-03   the-second-gunslinger     the second 24-chamber seat
    2026-09-03   the-archivist             the single-writer seat

**It is kept deliberately, and it is not maintained as current.** This repository is the
*record of the idea*, not the running system — the drawings came before any agent existed, and
some of them describe a shape the live ka-tet has since moved past. That is the point of keeping
it. A thesis with no visible first draft reads as though it arrived finished, and none of them do.

Where the design is now implemented, and where it has since changed, is documented in the
**[ka-tet](https://github.com/indicaindependent/ka-tet)** and in
**[the-gunslinger](https://github.com/indicaindependent/the-gunslinger)**.

It documents how one AI agent decides *which kind of expert to be* before it
answers, and why that decision is made mechanically instead of by vibe.

---

![The Gun](assets/exports/24-chamber-revolver.png)

---

## THE IDEA IN ONE PARAGRAPH

An agent that claims 24 specialities has none of them. A job title is not a
capability — a **researched, dated, source-cited working brief** is. So each of
the 24 disciplines here holds a real brief, and the router refuses to fire a
chamber whose brief has gone stale.

The metaphor is a revolver, and it is load-bearing rather than decorative:

| Term | Component |
| :--- | :--- |
| **The master** | The operator. Names the target. Never has to name the tool. |
| **The gunslinger** | The agent. Chooses the round and fires it. |
| **The gun** | The router — a machine-readable roster plus a fixed procedure |
| **The 24 chambers** | 24 expert skillsets, one loaded at a time |
| **A bullet** | One live-researched working brief |
| **A fully formed bullet** | A brief that passes an automated conformance gate |
| **The journal** | Per-chamber research and expiry dates |
| **Maintenance** | The 30-day freshness refresh |

---

## GALLERY

### Two layers

The permanent router identity sits above 24 swappable expert mounts. The router
is **not** one of the 24 — it is the thing that operates them.

![Two Layers](assets/exports/two-layer-architecture.png)

[Asset card](catalog/diagrams/two-layer-architecture.md)

---

### The firing sequence

Eight steps, two mandatory stops. Both stops are fail-safes rather than delays.

![The Firing Sequence](assets/exports/firing-sequence.png)

[Asset card](catalog/diagrams/firing-sequence.md)

---

### The ledger

The 24 briefs produced 241 concrete action items. Left as prose inside 24
documents, they would have evaporated. So they get extracted, assigned an owner,
and rated by blast radius.

![The Ledger](assets/exports/findings-ledger.png)

[Asset card](catalog/diagrams/findings-ledger.md)

---

### Palette

Every colour carries a measured contrast ratio. Nothing here was chosen because
it looked nice on one monitor.

![Palette](assets/exports/palette-contrast.png)

[Asset card](catalog/branding/palette-contrast.md)

---

## THREE RULES THAT SHAPED EVERY ASSET

**1. Text always sits on a solid card.**
Glow, scanlines and chromatic aberration are gone — not for taste, but because
they are a photosensitivity hazard and they destroy the crisp edges that contrast
measurement depends on. Once text is on a known solid surface, its contrast is
*provable* instead of situational.

**2. One data series is one colour.**
Every bar in the ledger chart is the same teal. Giving each bar its own hue
encodes nothing the label does not already state, and it is the fastest way to
make a chart look like a toy.

**3. The diagram carries its own labels.**
A chart whose legend lives only in a caption fails anyone who needs to zoom. The
chamber index is inside the image, at 14px minimum, on a solid background so the
asset never inherits an unknown page colour.

These are not house style. They are rulings from a colour-and-accessibility
research pass, applied to the assets that pass ruled on — including a finding
that the agent's own earlier logo files violated them.

---

## WHAT IS IN HERE

```
assets/
  vectors/       SVG sources - zoom-safe, the real deliverable
  exports/       PNG renders for fast preview
  palettes/      design tokens with computed contrast values
catalog/         one card per asset: what it shows, why, what broke
docs/            the architecture, the principles, the chamber roster
```

| Document | What it covers |
| :--- | :--- |
| [Architecture](docs/gun-architecture.md) | The two layers, the firing sequence, the freshness rule |
| [Design principles](docs/design-principles.md) | The accessibility and colour rulings, and their sources |
| [The 24 chambers](docs/the-24-chambers.md) | Every chamber, its trigger, and what it governs |
| [Palette](docs/palette.md) | Measured contrast for every token |

---

## AN HONEST NOTE ABOUT THE PRETTY PICTURES

Every diagram in here was generated, then **verified against its own rules** —
and three of them failed the first time.

| Failure | How it was caught |
| :--- | :--- |
| The hero image silently cut off 9 labels | Comparing text coordinates to the canvas, not looking at it |
| Letter-spacing passed into the text-anchor slot, emitting invalid SVG | Enumerating every anchor value actually present in the output |
| Two counting bugs that mis-stated the findings total | Two independent parsers disagreeing, then tracing the exact gap |

The generator now refuses to write an asset that overflows its canvas, uses an
invalid anchor, carries a blur filter, or drops type below 12px. That guard was
tested by feeding it a deliberately broken diagram to confirm it says no.

Which is rather the point of the whole system: a thing that looks finished is not
the same as a thing that was checked.

---

## LICENSE

Design assets in this repository are shared for viewing and reference. The
architecture and the diagrams are free to learn from. Ask before reusing the
marks as your own identity.
