# FIFA World Cup 2026 — Form vs. Chalk

An interactive visualization of the group stage answering two linked questions: which teams beat (or missed) their pre-tournament expectation, and which groups produced the closest matches — built as a single self-contained `index.html`.

## Audience & purpose

Casual football fans browsing after the group stage wraps, who want to see who over/under-performed their pre-tournament billing, and which groups were nail-biters vs. formalities. Assumed audience/tone carried over from the sibling `fifa-2026-group-competitiveness` project since the user did not specify otherwise.

## What it includes

- **Hero** — framing + tournament-wide stat counters (teams that matched expectation, upset count, tightest/loosest group).
- **Form vs. chalk overview** — all 48 teams plotted by expected rank (Elo-based) vs. actual group finish; most held (33/48 finished exactly as expected), with a handful of standout over/under-performers called out.
- **Upset spotlight** — cards for the clearest overperformers (South Africa, Cabo Verde, both jumping 2 spots) and underperformers (Portugal, Uruguay, Saudi Arabia among others, each dropping 1 spot).
- **Closeness spectrum** — all 12 groups ranked by average goal margin per match, tightest (Group H, 0.83) to most lopsided (Group I, 2.83).
- **Group explorer** — sortable/filterable table of all 12 groups with standings, expected-vs-actual, and per-match margins, so a user can cross-reference "was this a close group AND an upset group" (e.g. Group H was both the tightest group and home to Cabo Verde's upset).
- Dark/light toggle.

## Analytical method

- **Expected rank** = order within a 4-team group by pre-tournament Elo rating (highest Elo = rank 1).
- **Upset score** = expected_rank − actual_rank (positive = overperformed, negative = underperformed), actual rank from final standings (points, then goal difference, then goals for).
- **Closeness rank** = mean absolute goal margin across a group's 6 matches (lower = closer), same method as the sibling project, computed independently here for cross-reference with upset data.

## Data

[FIFA World Cup 2026 Dataset](https://www.kaggle.com/datasets/mominullptr/fifa-world-cup-2026-dataset) (Kaggle) — same source as `fifa-2026-group-competitiveness`, reused rather than re-pulled. Curated analysis lives in `data/fifa-2026-upsets-and-closeness/`.

**Caveat:** per the source repo, this is a generated/simulated dataset, not an official FIFA feed. "Expected rank" is Elo-based only — it does not account for group draw difficulty, injuries, or in-tournament form changes, so "upset" here means "beat the pre-tournament Elo ordering," not a claim about true underlying quality.

## Accessibility

Status is marked with icons/labels alongside color (not color alone); all text meets contrast minimums in dark and light mode; every chart value has an adjacent numeric label.
