# The Firing Sequence

**Asset:** `firing-sequence.svg`  
**Canvas:** 1180 x 900  
**Vector:** 10 KB  |  **PNG export:** 83 KB  
**Group:** diagrams

![The Firing Sequence](../../assets/exports/firing-sequence.png)

## What it shows

The eight-step routing procedure, including both mandatory stops.

## Design decisions

- Step 1 is always resolving live time. A prompt timestamp is stale by construction.
- Two red stops: a brief older than 30 days, and genuine ambiguity about which chamber applies.
- The ambiguity stop was built BEFORE the routing logic. Fail-safe before feature.

## Accessibility

| Property | Value |
| :--- | :--- |
| Solid background | Yes, never transparent |
| Minimum type size | 13px |
| Maximum type size | 34px |
| Blur or glow filters | None |
| Emoji | None |
| `role`, `title`, `desc` | Present |
