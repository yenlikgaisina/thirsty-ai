# 💧 Thirsty AI — Britain's Data Centre Boom vs Its Water Crisis

The first postcode-level interactive map of proposed and planned UK data centre schemes, overlaid on areas classified as **seriously water-stressed** by the Environment Agency. Search any UK postcode to see which AI server farms are planned near you — and whether they sit where water is already scarce.

**Live map:** https://yenlikgaisina.github.io/thirsty-ai/

> **This is an open dataset built to be corrected and reused.** Spotted an error, a missing scheme, or a better source? Open an issue or a pull request. See [Contributing](#contributing).

---

## Why this exists

Data centre planning applications in England roughly doubled in 2025, and from 8 January 2026 large data centres can use the Nationally Significant Infrastructure Project (NSIP/DCO) fast-track route. Around 140+ schemes have been proposed. Yet the UK has **no central register** of data centre planning applications — they are scattered across roughly 300 council portals with inconsistent descriptions and capacity figures often buried in PDFs.

At the same time, much of England — the South East, East of England, parts of the Midlands and South West — is officially classified as in *serious water stress*. This project joins the two: where are the data centres proposed, and how many of them land in water-stressed areas?

## Headline findings (from this register)

- **72** proposed / planned schemes compiled (announced, submitted, approved or under construction as of June 2026 — none yet operational).
- **~79%** of England-based schemes in the register sit in water-company areas classified as *seriously water-stressed* (EA 2021).
- **~9.8 GW** of disclosed capacity across the 39 of 72 schemes that publish a megawatt figure.
- **45** schemes fall within water-stressed areas.

These are figures for *this register*, which is a best-effort compilation rather than an exhaustive one. Treat them as indicative and verify against primary sources before publication.

## What's in the repo

| File | What it is |
|---|---|
| `index.html` | The self-contained interactive map (Leaflet + open postcodes.io search). No build step — open it or host it anywhere static. |
| `data/sites.json` | The full dataset, one object per scheme. |
| `data/sites.csv` | The same dataset as CSV for spreadsheet users. |

## Data dictionary

| Field | Meaning |
|---|---|
| `id` | Stable row identifier |
| `name` / `scheme` | Scheme name |
| `dev` / `developer` | Developer or promoter (best available) |
| `loc` / `location` | Town + county |
| `region` | UK region / nation |
| `lat`, `lng` | Approximate town-level coordinates (not exact site boundaries) |
| `mw` / `capacity_mw` | Reported capacity in MW, or blank if undisclosed |
| `mwNote` / `capacity_note` | Notes on capacity (phasing, conflicting figures, etc.) |
| `status` / `planning_status` | announced / submitted / approved / under construction / refused-appealed / paused |
| `company` / `water_company` | Water company serving the area (best guess) |
| `stress` / `water_stressed` | `true` if in an EA 2021 *serious water stress* company area |
| `flag` / `flags` | Verification notes and caveats for that row |
| `src` / `source_url` | Source URL |
| `planning_ref` | Council/PINS planning application reference, or "not located" (never invented) |
| `planning_url` | Direct link to the planning record where the reference appears |
| `ref_confidence` | How the reference was verified: confirmed-portal / confirmed-council / confirmed-decision-letter / confirmed-govuk / confirmed-public-notice / press-cited / partial / not-located |

## Methodology

Each row is a publicly reported UK data centre scheme, compiled from industry trackers, the House of Commons Library, government announcements, regional and local press, and campaign-group coverage. Water-company areas determined to be in *serious water stress* by the Environment Agency's 2021 classification are flagged. Per-site daily water use, where shown in the map, is estimated using broad per-MW ranges drawn from the UK Government's 2025 report on water use in AI and data centres; because cooling technology is rarely disclosed, every figure is a **range** with wide uncertainty, never a single number.

The per-MW band is derived from the two anchor figures in the Government report’s Section 2 table: ~20,000 L/MW/day (an average 100 MW site using ~2 million litres/day, cooling only) up to ~68,500 L/MW/day (a 100 MW hyperscale facility using ~2.5 billion litres/year). People-equivalent comparisons use the report’s own equivalence (~800 people per MW). These figures cover cooling only and exclude water embedded in electricity generation.

**Water-company boundaries.** Boundary-uncertain sites were verified by point-in-polygon queries against the official Appointed Water Supply Boundary feature services published by the water companies on the Stream open data portal (streamwaterdata.co.uk, CC BY 4.0). Thames Water and South East Water do not publish boundary services; sites confirmed inside a neighbouring company’s polygon were assigned to it, and one site (Custodian Dartford) remains flagged — but both candidate companies there are seriously water-stressed, so it cannot affect the headline statistic.

**Planning references.** For the larger schemes we record the council or Planning Inspectorate application reference (`planning_ref`) and a direct link (`planning_url`), with a `ref_confidence` note. References were taken from council portals, committee reports, decision letters, gov.uk and planning press. Where a reference could not be confirmed it is recorded as "not located" — never guessed or invented.

## Important caveats

- There is no central UK data centre planning register, so this compilation is **not exhaustive**.
- Capacity figures are frequently undisclosed or **conflict between sources** (flagged per row).
- Some "proposed" schemes will never be built; some are **paused** (e.g. Stargate / Cobalt Park); some consents are **under legal challenge** (e.g. Iver). Planning status is labelled per row.
- Water-company boundaries do not map perfectly to scheme locations; rows with **boundary uncertainty** are flagged.
- **Scotland and Wales sit outside the EA's England-only classification** and are shown as "not classified" — which does **not** mean water-abundant.
- Coordinates are approximate town centroids, not exact planning-application boundaries.

## Sources

- Environment Agency / DEFRA — Water stressed areas 2021 classification
- UK Government — Water use in AI and Data Centres report (2025)
- House of Commons Library — briefing CBP-10315 (data centres planning policy)
- DatacenterDynamics, Computer Weekly, Data Centre Review, Blackridge Research
- Foxglove and other campaign-group coverage; APRS data centre tracker; regional press

Per-row source URLs are included in the dataset.

## Contributing

Corrections and additions are very welcome — this is the kind of dataset that gets better with many eyes.

1. **Found an error or a missing scheme?** Open an issue with a source link, or edit `data/sites.json` and `data/sites.csv` and open a pull request.
2. Please include a **source URL** for any new or changed scheme.
3. Keep capacity figures as reported, and add a note in `flag` if sources disagree.
4. Flag any row where the water-company / water-stress mapping is uncertain rather than guessing silently.

## Licence

No licence is set yet. If you intend to reuse the data, please open an issue so an appropriate open licence (e.g. CC BY 4.0 for the data) can be added.

---

*Built as an open data-journalism project. Figures are indicative; always verify against primary sources before publication.*
