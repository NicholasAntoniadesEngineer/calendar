# Calendar

A self-contained relocation calendar & cash-flow planner — a single-page web app
with no build step or dependencies.

**Live:** https://nicholasantoniadesengineer.github.io/calendar/

## Usage

Open [`relocation-calendar.html`](relocation-calendar.html) directly in a browser.

Everything (markup, styles, and logic) lives in that one file, so there is nothing
to install or build.

## Saving your data

Your plan is **saved automatically in your browser** as you type — close the tab or
reload the page and everything (balances, credit cards, to-dos, calendar entries) is
exactly as you left it. There is no button to press for this.

To keep a **file copy** (for a backup, or to move the plan to another computer):

- **Save a copy** — writes the whole plan to one CSV file (`relocation-plan.csv`).
  When the page is served over http(s) (e.g. GitHub Pages or a local server) this
  shows a *Save As* dialog and then overwrites that same file on later saves. Opened
  directly from disk (a `file://` path) the browser can't show that dialog, so it
  downloads a copy to your Downloads folder instead.
- **Open** — loads a CSV file (or an older `.json` backup) back in.

The CSV is a single flat, spreadsheet-friendly sheet; every row is self-describing via
its first column (`record`): `meta` (settings), `bank` / `credit` / `owed`,
`todo_section` / `todo_item`, `day` (one row per calendar-day item) and `card` (credit
cards due). **Every calendar day in the visible range is written out** — even empty
ones — each with its weekday and a running daily total (those two columns are read-only
helpers and are ignored on import). Commas, quotes, accents and emoji in your text are
preserved exactly.
