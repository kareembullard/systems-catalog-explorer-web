# systems-catalog-explorer-web

Live: [https://kareembullard.github.io/systems-catalog-explorer-web/](https://kareembullard.github.io/systems-catalog-explorer-web/)

Browse my real personal systems catalog and follow its linked tools, use cases, and data flows.

## What it is

A static, single-file web app version of [systems-catalog-explorer](https://github.com/kareembullard/systems-catalog-explorer) (the original Flask + SQLite desktop app). This public version:

- Shows my **actual systems catalog** — 72 systems exported from my Airtable workspace, published deliberately
- Runs as a client-side single-page app with hash-based routing (`#/systems`, `#/system/<id>`, `#/tools`, `#/use-cases`, `#/data`) instead of a Flask backend — GitHub Pages only serves static files, so there's no server to route through
- Cross-links everything in both directions: a system page links to each of its tools/use cases/data items, and each of those has its own page listing every system that uses it
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

The `SYSTEMS` array embedded in `index.html` is a **curated superset of the raw links**: the Airtable export only had ~19 of 72 systems linked to anything, so the remaining mappings were filled in from the catalog's own tool/use-case/data vocabularies (no invented names — every linked item exists in the CSVs, and each data item keeps its Input/Output classification from `data.csv`). The raw link tables are kept as-is for reference; Airtable itself hasn't been updated with the curated links yet.

## Run locally

Just open `index.html` in a browser — no build step, no server required.

## Screenshot

_(placeholder)_
