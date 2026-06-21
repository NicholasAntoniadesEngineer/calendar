# Calendar

A self-contained relocation calendar & cash-flow planner — a single-page web app
with no build step or dependencies.

## Usage

Open [`relocation-calendar.html`](relocation-calendar.html) directly in a browser.

Everything (markup, styles, and logic) lives in that one file, so there is nothing
to install or build.

## Saving & loading your data

The toolbar offers two formats, both fully round-trippable:

- **Save JSON / Load JSON** — exact backup of the whole plan in one `.json` file.
- **Export CSV / Import CSV** — the whole plan as one spreadsheet-friendly `.csv`
  (`relocation-plan.csv`). Open it in Excel / Google Sheets to read or edit, then
  re-import.

The CSV is a single flat sheet; every row is self-describing via its first column
(`record`): `meta` (settings), `bank` / `credit` / `owed`, `todo_section` /
`todo_item`, `day` (one row per calendar-day item) and `card` (credit cards due).
**Every calendar day in the visible range is written out** — even empty ones — each
with its weekday and a running daily total (those two columns are read-only helpers
and are ignored on import). Commas, quotes, accents and emoji in your text are
preserved exactly.
