# Analyst → Narrator Handoff: groups-simple-scroll

## Chosen direction
**Combined: The Blowout Spectrum + Draws Aren't Equal** (two-act structure)

## Main claim
Group-stage closeness isn't binary (close vs. blowout) — it's a full spectrum, and even the "closest" category (draws) hides its own internal spectrum from true stalemates to shared shootouts.

## Act 1 — The Blowout Spectrum (all 72 matches)
Margin distribution across all matches:
| Margin | Matches | Share |
| --- | --- | --- |
| 0 (draw) | 20 | 28% |
| 1 | 18 | 25% |
| 2 | 16 | 22% |
| 3 | 9 | 12% |
| 4 | 5 | 7% |
| 5 | 2 | 3% |
| 6 | 2 | 3% |

- Over half the tournament (53%) was decided by a single goal or less.
- The two most one-sided matches tie at margin 6, but read completely differently: **Germany 7–1 Curaçao** (June 14, Group E) was a goal-fest (8 combined goals), while **Canada 6–0 Qatar** (June 18, Group B) was a shutout (6 goals, one side scored zero).
- Next tier (margin 5): **Senegal 5–0 Iraq** and **Portugal 5–0 Uzbekistan** — both clean-sheet blowouts.

## Act 2 — Draws Aren't Equal (20 draws)
Sorting the 20 draws by combined goals reveals they aren't one flat category:
- **Algeria 3–3 Austria** (June 27, Group J) — the lone true thriller draw, 6 combined goals, both teams attacking to the final whistle.
- A middle cluster of seven 1–1 draws (2 combined goals) — competitive but not chaotic.
- Seven scoreless **0–0** draws — true stalemates, including three of Group H's six matches involving Spain, Cape Verde, Uruguay, and Saudi Arabia.

## Evidence for Narrator
- Full dataset: `groups-simple-scroll/data/curated/matches_curated.csv` (72 rows, includes `margin`, `total_goals`, `is_draw`).
- Extremes table for Act 1 anchors: Germany 7–1 Curaçao, Canada 6–0 Qatar, Senegal 5–0 Iraq, Portugal 5–0 Uzbekistan.
- Draws ranked table for Act 2: Algeria 3–3 Austria at the top, seven 0–0s at the bottom (see `analyst_handoff.md` query in ledger for full list).

## Counterpoints / uncertainty
- Margin is a blunt instrument — it doesn't capture red cards, late collapses, or comeback drama within a match. The "goal-fest blowout vs. shutout blowout" distinction (Germany vs. Canada) is offered as a real but simple corrective, not a full narrative-tension score.
- "Closest" is capped by the data: with no extra time/penalties in the group stage, all 20 draws are mathematically tied at margin=0. The total-goals re-ranking is a defensible proxy for drama, not a claim that 3-3 is definitively "closer" than 0-0 — both are equally close on the scoreboard.

## Caveats that must remain visible
- No penalty shootouts occur in the group stage — draws are a real, valid outcome, not "incomplete" data.
- Goal-minute (stoppage-time drama) data was not available for most matches; the story should not imply timing details it doesn't have.
- Home/away labels are nominal (neutral multi-host tournament).

## Possible chart forms (for Designer, not yet chosen)
1. Diverging/sorted margin chart — one mark per match, sorted or arranged by margin, colored/split by draw vs. decisive.
2. Beeswarm or dot-strip of margin values — shows the distribution shape and clustering at low margins.
3. Small-multiples or ranked list specifically for the 20 draws — total-goals bar/dot per draw, isolating Act 2.
