# The Ledger

**Asset:** `findings-ledger.svg`  
**Canvas:** 1240 x 940  
**Vector:** 22 KB  |  **PNG export:** 67 KB  
**Group:** diagrams

![The Ledger](../../assets/exports/findings-ledger.png)

## What it shows

241 action items extracted from the 24 briefs, grouped by owner and by blast radius.

## Design decisions

- Bars are ONE colour because they are one data series. Per-item colour would encode nothing the label does not already say.
- Ownership matters more than count. Most items are not the agent's own to execute.
- Blast radius, not defect severity, decides priority.

## Defect found while building it

Two counting defects surfaced while building this: nested sub-bullets were counted as separate items, and real table rows were discarded as headers because a citation column contained the word 'Step'.

## Accessibility

| Property | Value |
| :--- | :--- |
| Solid background | Yes, never transparent |
| Minimum type size | 12px |
| Maximum type size | 36px |
| Blur or glow filters | None |
| Emoji | None |
| `role`, `title`, `desc` | Present |
