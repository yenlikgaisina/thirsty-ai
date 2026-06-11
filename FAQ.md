# Thirsty AI — Defence FAQ

Every claim on this page links to its source. Water-demand figures come from the UK government's own 2025 report, *Water use in AI and Data Centres* (GDSA), unless stated otherwise. Where this project's figures differ from others', the difference is explained, not hidden.

**Source:** GDSA report, 2025 — https://assets.publishing.service.gov.uk/media/688cb407dc6688ed50878367/Water_use_in_data_centre_and_AI_report.pdf

---

### "Modern data centres use closed-loop cooling — they barely use water."

True for some facilities, and where cooling technology is disclosed, the data reflects the low end of the range. That is exactly why every figure on this site is a range, not a single number — and why the bigger finding stands either way: cooling technology is undisclosed for the overwhelming majority of these 72 schemes, and only two-fifths of operators track their water use at all (GDSA report, Section 4: "only two-fifths of data centre operators actively track their water usage metrics"). If a developer publishes its cooling design and water forecast, it will be added to the dataset — that is what it is for.

### "Most of these will never be built."

Correct, and the site says so. Every row carries its planning status — announced, submitted, approved, under construction, paused, or under legal challenge. The dataset maps the pipeline, because the pipeline is what water-resource planning has to absorb — and current water resource management plans do not account for data centre demand (House of Commons Library, "Future water resources", CBP-10248 — https://commonslibrary.parliament.uk/research-briefings/cbp-10248/).

### "Data centres use far less water than agriculture or leaks."

Nationally, yes. Locally, no — that is the point of a map. A hyperscale facility's demand is concentrated in one supply zone, and 79% of England's proposed sites are in zones already classified seriously water-stressed. Thames Water has previously warned data centres of restrictions during heatwaves and objected to applications on water grounds (GDSA report, Section 4: "Thames Water, for example, had warned data centres of potential restrictions during heatwaves and even objected to planning applications for new data centres due to water concerns").

### "Your 79% doesn't match Chatham House's 84%."

They measure different things: the 84% figure is UK-wide and forward-projected; this project's 79% is England-only, measured against the Environment Agency's current water-stress classification, and counted by scheme. Two independent methods landing within five points of each other is corroboration, not contradiction.

### "Scotland and Wales are shown as 'not classified' — isn't that misleading?"

The Environment Agency classification legally covers England only. "Not classified" means exactly that — it does not mean "water-abundant". This is stated on the site and in the README.

### "These water estimates are made up."

Every per-MW figure comes from the UK government's own 2025 report (*Water use in AI and Data Centres*, GDSA), cited to section. The site's 20,000–68,500 L/MW/day band is derived from that report's figures. Estimates are labelled as estimates, presented as ranges, and the methodology is public. The alternative to estimating is silence — which is what the 33 schemes that disclose no power figure would prefer.

### "Why do your disclosure counts say 39 and 33?"

Of the 72 mapped schemes, 39 disclose a power figure (totalling 9,788 MW, ≈ 9.8 GW) and 33 do not. Note: the PACE West Midlands figure (168 MW) is a three-site portfolio total stored at site level; counting it as a single row is the dataset's deliberate, documented choice.

---

*This FAQ is part of the open Thirsty AI dataset (CC BY 4.0). Corrections welcome via the repository: https://github.com/yenlikgaisina/thirsty-ai*
