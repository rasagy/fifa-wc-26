# Curator → Analyst Handoff: groups-simple-scroll

## Dataset location
- Raw: `groups-simple-scroll/data/raw/matches_raw.csv`
- Curated: `groups-simple-scroll/data/curated/matches_curated.csv`

## Source
All 72 group-stage matches (12 groups A–L, 4 teams each, round-robin, 6 matches per group) sourced from the individual Wikipedia group pages for the 2026 FIFA World Cup (e.g. `en.wikipedia.org/wiki/2026_FIFA_World_Cup_Group_A` through `..._Group_L`), fetched 2026-07-03. Tournament ran June 11–27, 2026 for the group stage.

## Data dictionary
| Field | Type | Description |
| --- | --- | --- |
| `group` | string (A–L) | Group letter |
| `date` | date (ISO) | Match date |
| `matchday` | int (1–3) | Group matchday number |
| `home_team` / `away_team` | string | Team names as listed on the fixture (home/away is nominal — neutral-venue tournament, not home advantage) |
| `home_score` / `away_score` | int | Final goals scored |
| `margin` | int | `abs(home_score - away_score)` — core "closeness" metric |
| `total_goals` | int | `home_score + away_score` |
| `is_draw` | bool | `margin == 0` |
| `winner` / `loser` | string | Team names, or `"Draw"` for both fields when `margin == 0` |

## Transformation log
1. Compiled raw match list (`matches_raw.csv`) from 12 Wikipedia group-page fetches, one row per match.
2. Derived `margin`, `total_goals`, `is_draw`, `winner`, `loser` via `python3` script into `matches_curated.csv`. No filtering, imputation, or deduplication was needed — all 72 matches had complete scores.

## Known caveats
- **No penalty shootouts or extra time** — group stage matches are all single 90(+stoppage)-minute results, so `margin = 0` (a draw) is the practical floor for "closeness"; there is no data-driven way to rank *among* draws by closeness except by drama proxies (e.g. total goals, or goal timing where available).
- **Goal-minute data is incomplete** — only Group A's fetch returned goal-by-goal minutes; the rest of the dataset has final scores only. If the Analyst/Narrator want a "decided in stoppage time" angle, that would require additional per-match enrichment (flagged as an open callback to Curator, not fabricated here).
- **Home/away labels are nominal** — 2026 is a neutral-multi-host tournament (US/Mexico/Canada); "home" doesn't imply home-field advantage except for the three host nations' own matches.
- **48-best-third-place-team format** — advancement isn't purely group-1st/2nd, so any "which teams advanced" framing needs the third-place qualification rule accounted for; this dataset only contains match results, not the qualification table.

## Recommended analytical questions
1. Which single match was the most one-sided by margin, and does high margin also mean a high-scoring game (blowout) or a shutout (defensive lopsidedness)?
2. Since margin=0 is a floor, which draws were the most "alive" (highest combined goals) vs. the most cagey (0-0)?
3. Do some groups play systematically tighter or more lopsided than others (avg margin per group)? Is there a pattern (e.g. groups with a big favorite vs. evenly-matched groups)?
4. How common are truly one-goal nail-biters (margin = 1) vs. blowouts (margin ≥ 4) across the full 72-match set — what's the actual shape of the closeness distribution?
