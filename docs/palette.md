# PALETTE

Contrast values are **computed from the hex values**, not asserted. Standard is
WCAG 2.2: 4.5:1 for normal text, 3:1 for large text and UI components.

![Palette](../assets/exports/palette-contrast.png)

| Token | Hex | Role | vs background | vs card |
| :--- | :--- | :--- | ---: | ---: |
| `bg` | `#0B1015` | page surface | 1.0:1 | 1.14:1 |
| `card` | `#161E27` | raised panel | 1.14:1 | 1.0:1 |
| `card2` | `#1E2833` | inset panel | 1.28:1 | 1.13:1 |
| `border` | `#33424F` | hairline rule | 1.85:1 | 1.63:1 |
| `text` | `#F3F7F9` | primary text | 17.73:1 | 15.6:1 |
| `muted` | `#A7B6C2` | secondary label | 9.2:1 | 8.1:1 |
| `teal` | `#2DD4E8` | accent, focus ring, single-series data | 10.64:1 | 9.36:1 |
| `magenta` | `#E87BC8` | second category only | 7.37:1 | 6.48:1 |
| `amber` | `#F5A524` | credential-class emphasis | 9.36:1 | 8.24:1 |
| `red` | `#FB7185` | hard stop, harm class | 7.1:1 | 6.25:1 |
| `green` | `#4ADE80` | engineering group | 10.96:1 | 9.65:1 |
| `violet` | `#A78BFA` | science group | 7.02:1 | 6.18:1 |

---

## Three rules

**Text always sits on a solid card.** Never on a gradient, never on decoration.
Once text is on a known solid surface its contrast is provable rather than
situational.

**One data series is one colour.** Per-item hues encode nothing the label does not
already state.

**No glow, no scanlines, no chromatic aberration.** A photosensitivity hazard, and
they destroy the crisp edges that contrast measurement depends on. The accent teal
survives because it does a real job as a focus colour.

## Why every asset has a solid background

A transparent SVG inherits whatever colour the host page uses, which makes its text
contrast unprovable. Every asset here paints its own background first.
