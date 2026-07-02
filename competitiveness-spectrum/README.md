# FIFA World Cup 2026 — Group Stage Spectrum

An interactive scrollytelling story ranking all 12 FIFA World Cup 2026 groups from closest competition to clearest separation, built as a single self-contained `index.html`.

## Audience & purpose

Casual football fans browsing after the group stage wraps, who want a fast, visual answer to "which groups were actually competitive?" rather than a raw standings dump.

## Personality

Studio / cinematic — full-bleed sections, scroll-snap, teal-to-red accent gradient tied to each group's rank, animated bar fills and counters on scroll reveal. Chosen over a more restrained editorial or dashboard treatment because the story is inherently a ranked spectrum and benefits from visual drama at the extremes (Group H's nail-biter vs. Group I's blowouts).

## What it includes

- **Hero** — framing + tournament-wide stat counters (goals, one-goal games).
- **Overview ranking chart** — all 12 groups as horizontal bars sorted by average goal margin per match, clickable to jump to that group's section.
- **12 full-bleed group sections** (ranked, not alphabetical) — standings table, competitiveness stat tiles (avg margin, goals, draws, blowouts), and all 6 match results as score cards with an animated margin bar per match.
- **Closing section** — narrative recap, a clickable strip of all 12 groups, and data source/caveat note.
- Dark/light toggle and a right-rail dot nav for jumping between sections.

## Analytical method

Competitiveness rank = mean absolute goal margin across a group's 6 matches (lower = closer), tie-broken by points spread then goal-difference spread across the final table. This directly measures "how close were the actual games," rather than inferring closeness from final standings alone.

## Data

[FIFA World Cup 2026 Dataset](https://www.kaggle.com/datasets/mominullptr/fifa-world-cup-2026-dataset) (Kaggle, mirrored on GitHub at mominullptr/FIFA-World-Cup-2026-Dataset) — group-stage match results for all 48 teams / 72 matches. Curated snapshot and analysis script live in `data/fifa-2026-worldcup/`.

**Caveat:** per the source repo, this is a generated/simulated dataset (not an official FIFA feed) for a tournament dated in the system's current period (July 2026), beyond the assistant's training cutoff. Figures should be treated as illustrative, not authoritative — this is distinct from the earlier `/fifa-2026` artifact in this repo, which was built from Wikipedia scraping rather than a single sourced dataset.

## Accessibility

Status dots (not color alone) mark top-2 teams in standings tables; all text meets contrast minimums in both dark and light mode; every bar/chip has an adjacent numeric or text label.
