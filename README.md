# Calendar

A self-contained relocation calendar & cash-flow planner — a single-page web app
with no build step or dependencies.

## Usage

Open [`relocation-calendar.html`](relocation-calendar.html) directly in a browser.

Everything (markup, styles, and logic) lives in that one file, so there is nothing
to install or build.

## Saving & loading your data

- **Save** — writes the whole plan to one CSV file (`relocation-plan.csv`). The first
  Save asks where to put it; **every Save after that silently overwrites that same
  file** — no dialogs, no duplicate copies. (Uses the browser File System Access API,
  available in Chrome / Edge; other browsers fall back to a normal download.) The file
  it's writing to is shown next to the button.
- **Open** — loads a plan back and remembers the file, so the next Save overwrites it.
  It opens the CSV you saved, and still reads older `.json` backups too.

The CSV is a single flat, spreadsheet-friendly sheet; every row is self-describing via
its first column (`record`): `meta` (settings), `bank` / `credit` / `owed`,
`todo_section` / `todo_item`, `day` (one row per calendar-day item) and `card` (credit
cards due). **Every calendar day in the visible range is written out** — even empty
ones — each with its weekday and a running daily total (those two columns are read-only
helpers and are ignored on import). Commas, quotes, accents and emoji in your text are
preserved exactly.
