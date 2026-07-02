# PRODUCT.md — groups-simple-scroll

Product-context brief for the Designer stage. Companion to `README.md` (project overview) and `groups-simple-scroll.md` (stage-by-stage ledger). This file documents both the original brief and the design decisions actually built into `index.html`, so a future revision can pick up the system without re-deriving it.

## What this is
A single self-contained scrollytelling HTML page telling one story: FIFA World Cup 2026 group-stage closeness isn't binary. It walks through all 72 real matches on a margin spectrum (Act I), then zooms into the 20 drawn matches to show even "close" games aren't equally close (Act II).

## Audience
General football fans following the 2026 tournament — casual readers who know the basics of the sport but want a fast, visually engaging way to relive the group stage's tightest and most lopsided results.

## Purpose
Surface real, evidence-backed insights beyond a simple "biggest margin" list. Every claim on the page traces back to `data/curated/matches_curated.csv`.

## Format
Single self-contained HTML file (`index.html`), viewable standalone in a browser, responsive down to ~390px mobile widths. Fonts load from Google Fonts (falls back to system condensed/sans stacks offline); everything else — data, styles, charts, interaction — is inline with no other external dependencies.

## Personality / tone
Energetic, editorial, confident — treats the data like a sportswriter would, not like a spreadsheet. Avoids generic dashboard phrasing ("Key Metrics", "Overview") in favor of specific, claim-driven language (see `data/curated/narrator_story_brief.md` for the full copy brief and anti-trope pass).

## Anti-references
- Generic BI dashboards with KPI tiles and no narrative thread.
- Stock clip-art soccer balls / trophy emoji as the primary visual language.
- Walls of unlabeled bar charts with no annotation or story beats.

## Design principles
- Every chart carries a specific, real claim — not just "here is the data."
- Closeness and lopsidedness are encoded as a clear visual spectrum, not just a sorted table.
- Real match data only — no fabricated or estimated results.

## Visual system (as built)

**Style family:** Stadium broadcast — dark, high-energy, floodlit.

**Background:** Page-wide mowed-grass gradient (dark green vertical gradient + subtle repeating stripe texture + floodlight radial glows), replacing the earlier flat navy. Chart/callout/tile panels sit on top in navy (`--bg-card`, `--bg-raised`) so they read as scoreboard panels over grass.

**Hero:** An SVG pitch diagram (touchlines, halfway line, center circle, both penalty boxes + six-yard boxes + penalty arcs, corner arcs, goal posts — scaled from real 105m×68m pitch proportions) sits behind the title at low opacity (0.16 stroke).

**Typography:**
- Display (`--font-display`: Barlow Condensed, weight 900, italic) — all headings (`h1`–`h3`), eyebrow labels (`.kicker`, `.section-kicker`), and every scoreboard-style number (hero stats, callout scores, draw-tile scores, tooltip score).
- Body (`--font-body`: Inter, 400–700) — subtitle, section copy, legends, captions, tooltip meta text, caveats, footer.

**Chart form:** Beeswarm / dot-strip. Act I plots all 72 matches along a margin axis (0–6); Act II plots the 20 draws along a total-goals axis. Dot size encodes total goals scored.

**Color:** 12-hue categorical palette (`--group-a` … `--group-l`), one hue per FIFA group, sweeping monotonically across the spectrum in alphabetical order (red → orange → gold → green → teal → blue → violet → magenta) so hue order visually matches letter order. OKLCH-derived and validated against the dark page surface via the dataviz skill's six-checks script — lightness band, chroma floor, and contrast all pass; colorblind separation sits at the legal 8–12 floor, mitigated by the always-visible 12-item group legend plus the hover tooltip (both act as the required secondary encoding).

**Interaction:**
- Hover/focus on any dot shows a tooltip with score, group, and date.
- Hover/focus on a legend swatch isolates that group's dots (dims all others to 0.12 opacity) in both the chart and the legend itself; clears on mouse-leave/blur.
- Legend swatches fade in with a ~35ms staggered entrance when scrolled into view (respects `prefers-reduced-motion`).
- The lone high-scoring draw tile (Algeria 3–3 Austria) glows in its own group's color (`--tile-accent`) rather than a fixed accent.

## Accessibility goals
- WCAG AA contrast for all text and key chart marks (validated against every background gradient stop, not just one surface).
- Chart information never depends on color alone — every dot's identity is also available via keyboard-focusable tooltip and the group legend.
- Reduced-motion path for all scroll-reveal and hover-scale animations.
- Legible down to ~390px mobile width; no horizontally-clipped content.

## Status
Complete. Final artifact: `index.html`. Full stage-by-stage decision log: `groups-simple-scroll.md`.
