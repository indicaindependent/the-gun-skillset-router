# Two Layers

**Asset:** `two-layer-architecture.svg`  
**Canvas:** 1200 x 880  
**Vector:** 14 KB  |  **PNG export:** 74 KB  
**Group:** diagrams

![Two Layers](../../assets/exports/two-layer-architecture.png)

## What it shows

How a task travels: the master names a target, Layer 0 resolves time and picks the chamber, one of 24 Layer-1 mounts loads.

## Design decisions

- Layer 0 is NOT one of the 24. It is the thing that operates them.
- The mount pin ends 'for the current date and time', which is why a live clock is mandatory rather than nice to have.
- Only one mount is loaded at a time. There is no blended-expert mode.

## Accessibility

| Property | Value |
| :--- | :--- |
| Solid background | Yes, never transparent |
| Minimum type size | 13px |
| Maximum type size | 36px |
| Blur or glow filters | None |
| Emoji | None |
| `role`, `title`, `desc` | Present |
