# Narrator → Designer Story Brief: groups-simple-scroll

## Audience & tone
General football fans, casual but attentive. Investigative frame — editorial voice, not dashboard voice. Short sentences near claims; caveats sit next to the numbers they qualify.

## Main claim / opening question
"Which World Cup 2026 group match was really the closest?" — the scoreboard says 20 matches tie at zero. This piece shows that tie conceals two very different kinds of closeness, and that the widest margins conceal two very different kinds of blowout.

## Story spine
1. **Hook** — pose the closeness question; state the flat fact that 20 of 72 matches ended level.
2. **Act 1: The Full Spread** — every one of the 72 matches arranged by margin, low to high. Turning point: the widest margin (6) is shared by two matches that don't feel alike — Germany 7–1 Curaçao (8 combined goals) and Canada 6–0 Qatar (a shutout).
3. **Act 2: The Zero Club** — zoom into the 20 drawn matches. They aren't identical either: Algeria 3–3 Austria is the only draw with more than 4 combined goals; seven matches finished 0–0, including three of Group H's six games.
4. **Takeaway** — the scoreboard can't distinguish a 0–0 from a 3–3, or a goal-fest blowout from a shutout blowout. This is what the numbers show; whether a match felt close is a separate question the margin alone can't answer.

## Titles & copy (post anti-trope edit)

**Main title:** Same Scoreboard, Different Game

**Subtitle:** Two matches finished with the same six-goal margin. Twenty finished level. None of them were the same game.

**Section header — Act 1:** The Full Spread
**Section header — Act 2:** The Zero Club

## Annotation priorities (in order)
1. On the margin-6 pair: "Germany 7–1 Curaçao and Canada 6–0 Qatar — the two most lopsided results of the group stage. Same margin, six goals apart in scoreline. One was a goal-fest. One was a shutout."
2. On the margin-0 cluster: "20 matches ended level — 28% of the entire group stage."
3. On Algeria 3–3 Austria: "The only draw with more than four combined goals. Algeria and Austria traded three goals each in Group J's final round, June 27."
4. On the 0–0 cluster: "Seven matches finished scoreless, including three of Group H's six games — Spain, Cape Verde, Uruguay, and Saudi Arabia."

## Caveat language (must remain visible)
- "Group-stage matches don't go to extra time or penalties — a draw is a final result, not an unresolved one."
- "Home/away order here follows the fixture listing at this neutral multi-host tournament, not home-field advantage."

## Evidence sequence for Designer
Full dataset: `groups-simple-scroll/data/curated/matches_curated.csv`. Key numbers already computed in `analyst_handoff.md` (margin distribution table, draws-by-total-goals table).

## Required language in the HTML artifact
- Main title and subtitle above must appear verbatim (or near-verbatim) as the page's primary heading.
- Both caveat lines must be visible somewhere in the artifact (footer or inline near the relevant chart), not omitted.
