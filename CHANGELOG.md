# Changelog

All notable changes to the Thirsty AI dataset and map. Dataset version is also recorded in `data/sites.json` (`_meta.version`).

## [0.3.0] — 2026-06-11
### Changed
- Water-use band now derived from the Government’s “Water use in AI and Data Centres” report (GDSA), Section 2: ~20,000 L/MW/day (cooling-only lower anchor) to ~68,500 L/MW/day (hyperscale upper anchor). Removed the “provisional” label.
- Replaced the ~350 L/household assumption with the report’s own equivalence (a 100 MW hyperscale facility ≈ the daily water needs of ~80,000 people; ~800 people per MW).
- Popup water line relabelled “Est. cooling water” and reports population-equivalent ranges.
### Added
- Methodology now cites cooling-reduction figures (cold-plate/immersion cut water 31–52% vs air), ~80% evaporative loss, England supply (~14,000 Ml/day) vs ~5,000 Ml/day projected 2050 deficit, and that only two-fifths of operators track water use.
- Footnote: Severn Trent’s Chester supply zone was excluded from the EA 2021 designation (no rows affected).

## v0.2 — 2026-06-11
- Redesigned map: full-viewport hero stat, animated counters (respects prefers-reduced-motion), Carto Dark Matter tiles, water colour palette (rust-orange = stressed, slate = not classified, grey = undisclosed).
- Added scrollytelling intro, league tables with deep-linkable URLs (?region=&stress=), transparency-gap visual, and shareable postcode result card.
- Added household-equivalent water comparisons (assumption: ~350 L/household/day), shown as ranges.
- Added OpenGraph / Twitter share metadata.
- Per-MW water band still PROVISIONAL pending figures from the Government 'Water use in AI and Data Centres' report.

## v0.1 — 2026-06-11
- Initial register of 72 proposed / planned UK data centre schemes (as of June 2026).
- Published index.html map, data/sites.json and data/sites.csv, and methodology README.

## Known TODOs (verification)
- Replace provisional per-MW water band with the Government report's published figures, cited by page.
- Point-in-polygon join for boundary-uncertain rows (Manor Farm, Google North Weald, Dartford, Iver cluster, Cranford, Havering) using Ofwat/EA water company shapefiles.
- Add council planning reference numbers + portal links for at least the top 20 schemes by MW.
