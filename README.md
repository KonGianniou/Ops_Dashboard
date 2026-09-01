# Support Ops Dashboard

A single-file, static HTML dashboard for visualizing support team analytics and roster performance. No build step, no backend — open it in a browser and it works.

![Static](https://img.shields.io/badge/type-static%20HTML-blue) ![No dependencies](https://img.shields.io/badge/backend-none-lightgrey)

## Features

**Analytics tab**
- Hero metric card for average first response time, with a trend sparkline and week-over-week delta
- Quick-stat list (tickets handled, CSAT, backlog)
- "This week / Last week" toggle that swaps all metrics on the page
- Volume by channel (bar chart)
- CSAT trend over the last 8 weeks (line chart with hoverable data points)
- Backlog by priority (P1–P4 breakdown)
- Hover tooltips on all charts

**Team tab**
- Quarterly OKR progress bars
- Manager's note panel for team context/callouts
- Sortable, searchable team roster table (click a column header to sort, type to filter by name)
- Expandable rows with per-agent notes
- Workload and trend indicators per agent

## Getting started

No installation required.

1. Download `support_ops_dashboard.html`
2. Open it directly in any modern browser (double-click, or drag into a browser window)

To serve it locally instead:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/support_ops_dashboard.html
```

## Tech stack

- Plain HTML, CSS, and vanilla JavaScript — no frameworks, no build tools
- [IBM Plex Sans / Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Sans) and [Fraunces](https://fonts.google.com/specimen/Fraunces) via Google Fonts (loaded over CDN)
- [Tabler Icons](https://tabler.io/icons) webfont via CDN

Both font and icon assets load from a CDN, so an internet connection is needed for full styling — the layout and functionality still work offline, just without the custom fonts/icons.

## Data

All data in this dashboard (tickets, CSAT scores, agent names, roster stats) is **hardcoded sample/demo data** directly in the HTML and JavaScript. There is no API call or database connection.

To use this with real data, you'll want to either:
- Manually edit the values in the `rangeData` object and the roster `<tr>` rows, or
- Replace the static markup with a small script that fetches and renders data from your actual support platform (e.g., Zendesk, Intercom, Freshdesk)

## Customization

Key things to tweak, all near the top of the `<style>` block:
- `:root` CSS variables control the color palette (`--coral`, `--teal`, `--amber`, etc.)
- `rangeData` (in the `<script>` section) controls what the week toggle displays
- Roster rows are plain `<tr>` elements in the `#roster-body` table — copy/edit/remove as needed

## Browser support

Works in any modern evergreen browser (Chrome, Firefox, Safari, Edge). Uses standard flexbox/grid CSS and vanilla DOM APIs — no polyfills included.

## License

© 2026 Konstantina Gianniou. All rights reserved.

This project, including its structure, design, and code, was created by Konstantina Gianniou and is shared here for portfolio and demonstration purposes only. It may not be reproduced, distributed, or used as the basis for a commercial product without explicit written permission from the author.

---

Built by Konstantina Gianniou — Customer Support Operations · Internal Tools · Portfolio 2026
