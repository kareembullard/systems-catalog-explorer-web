# systems-catalog-explorer-web

Live demo: [https://kareembullard.github.io/systems-catalog-explorer-web/](https://kareembullard.github.io/systems-catalog-explorer-web/)

Browse a sample systems catalog and follow its linked tools, use cases, and data flows.

## What it is

A static, single-file web app version of [systems-catalog-explorer](https://github.com/kareembullard/systems-catalog-explorer) (the original Flask + SQLite desktop app). This public version:

- Ships with a **generic example catalog** — 10 illustrative "systems" (Email Management, Content Publishing, Task Management, etc.) built from well-known, publicly-recognizable tools, not anyone's real personal setup
- Runs as a client-side single-page app with hash-based routing (`#/systems`, `#/system/<id>`, `#/tools`, `#/use-cases`, `#/data`) instead of a Flask backend — GitHub Pages only serves static files, so there's no server to route through
- Makes no network calls

Read-only, exactly like the original: browse systems, click into one to see its linked tools/use cases/data, or browse the full reference lists directly.

## Run locally

Just open `index.html` in a browser — no build step, no server required.

## Screenshot

_(placeholder)_
