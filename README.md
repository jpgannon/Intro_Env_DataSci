# Spreadsheet Activities Site

Source for the GitHub Pages site hosting in-class spreadsheet activity handouts.

## Structure

```
_config.yml                              site title + theme (GitHub Pages built-in "Cayman")
index.md                                 splash page, links to every activity
01-spreadsheet-fundamentals.md           Chapters 1–3
02-formulas-statfunctions-sorting.md     Chapters 5, 6, 18
03-importing-data-pivottables.md         Chapters 21, 22
assets/                                  downloadable CSV/xlsx files linked from the pages
```

## Editing a page

Open the `.md` file on github.com, click the pencil icon, edit, and click "Commit changes." The live site updates automatically within a minute or two — no local setup, git, or command line needed.

## Adding a new activity

1. Duplicate one of the existing `NN-*.md` files and rename it (e.g. `04-new-topic.md`).
2. Keep the front matter at the top:
   ```
   ---
   layout: default
   title: Your Page Title
   ---
   ```
3. Add a link to it from `index.md`.

## Adding a new downloadable file

Drop it in `assets/` and link to it from a page with `[link text](assets/filename.xlsx)`.
