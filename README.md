# systems-catalog-explorer-web

Live: [https://kareembullard.github.io/systems-catalog-explorer-web/](https://kareembullard.github.io/systems-catalog-explorer-web/)

Browse my real personal systems catalog and follow its linked tools, use cases, and data flows.

## What it is

A static, single-file web app version of [systems-catalog-explorer](https://github.com/kareembullard/systems-catalog-explorer) (the original Flask + SQLite desktop app). This public version:

- Shows my **actual systems catalog** — 72 systems exported from my Airtable workspace, published deliberately
- Runs as a client-side single-page app with hash-based routing (`#/systems`, `#/system/<id>`, `#/tools`, `#/use-cases`, `#/data`) instead of a Flask backend — GitHub Pages only serves static files, so there's no server to route through
- Cross-links everything in both directions: a system page links to each of its tools/use cases/data items, and each of those has its own page listing every system that uses it
- **Editable links, in every direction**: a system page has an "Edit Links" button to add/remove its tools, use cases, and data items. A tool/use-case/data page has its own "Edit" button — rename it everywhere it's used, toggle a checklist of every system it should link to, *and* link it directly to any Tool/Use Case/Data item independent of a system (a purely local, hand-drawn layer — the real Airtable data only connects these three through Systems, so this is for sketching relationships that don't formally exist yet). Edits save to *your* browser's `localStorage` as an overlay on top of the baked-in data — they don't touch the source files. Export/Import buttons at the top of the page let you back up edits or hand them off (to me, to sync into the real Airtable base)
- Makes no network calls

## Where the data comes from

`data/` holds the raw CSV export from the Airtable base (the same files the desktop app imports):

| File | Contents |
|---|---|
| `systems.csv` | 72 systems |
| `tools.csv` | 94 tools, with function/area classification |
| `use_cases.csv` | 176 use cases |
| `data.csv` | 267 data items, with Input/Output classification |
| `systems_tools.csv`, `systems_use_cases.csv`, `systems_data.csv` | link tables |

The `SYSTEMS` array embedded in `index.html` is a **curated superset of the raw links**: the Airtable export only had ~19 of 72 systems linked to anything, so the remaining mappings were filled in from the catalog's own tool/use-case/data vocabularies (no invented names — every linked item exists in the CSVs, and each data item keeps its Input/Output classification from `data.csv`). The raw link tables are kept as-is for reference. Airtable itself has since been updated to match these curated links, so the base, the desktop app, and this site all agree.

## Run locally

Just open `index.html` in a browser — no build step, no server required.

## Screenshot

_(placeholder)_
