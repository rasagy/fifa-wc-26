# FIFA World Cup 2026 — Group Stage Visualization

An interactive visualization summarizing the group stages of the FIFA World Cup 2026. Built as a single self-contained `index.html` in this folder.

## What it includes

- **Third-place qualification race** — the 12 third-place finishers ranked with a dashed cutoff line showing exactly which 8 advance to the Round of 32.
- **12 group cards** (A–L) with standings tables, color-coded by status (auto-qualified / qualified via third-place / eliminated), each expandable to show all 6 match results with scores, dates, and venues.
- **Search box** that highlights a team across every group and the third-place race simultaneously.
- **Flat sortable table view** of all 48 teams as an alternative to the card grid.
- **Dark mode toggle**, using the status-color system (good/muted) rather than arbitrary hues, per the dataviz skill's accessibility rules.

## Data

Final group-stage standings and match results for all 12 groups, sourced from Wikipedia's per-group articles, cross-checked against the third-place qualification order.

**Caveat:** this data reflects a tournament dated in the system's current date (July 2026), which is beyond the assistant's actual training cutoff — it was pulled live via web search/fetch rather than from memory, so it should be treated as only as reliable as those sources.
