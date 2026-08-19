---
layout: default
title: Importing Data & PivotTables
---

# Importing Data & PivotTables
*New River Valley Monitoring Network — 2025–2026 Visit Log*

This activity covers importing external data and building PivotTables/PivotCharts in Excel and Google Sheets. It follows Chapters 21 and 22 of [The Most EXCELlent OER Spreadsheets Textbook](https://minnstate.pressbooks.pub/spreadsheets2025/) (Lacher, 2025), an open-access resource you can revisit any time for more detail or extra practice.

*A note on scope: Chapter 22 opens with importing data from a Microsoft Access database. That's a real skill, but it needs Windows Excel with an Access driver installed, so it doesn't work for everyone in a mixed Excel/Sheets/Mac room — and in practice, environmental data (USGS, EPA, NOAA) is almost always distributed as CSV or accessed through the web anyway. This activity substitutes those two import paths, which is what the rest of Chapter 22 covers.*

*All discharge and turbidity values in the dataset are illustrative, built from the same seasonal pattern used in earlier activities — not real gauge records.*

## Part 1: Import Data from a Text File

You've been given [nrv-monitoring-log.csv](assets/nrv-monitoring-log.csv) — 96 rows covering 4 sites, visited monthly across 2025–2026.

- In Excel: Data tab > Get Data > From File > From Text/CSV. Locate nrv-monitoring-log.csv and select it.
- Excel will show a preview and try to detect the delimiter (comma) and data types automatically. Confirm the VisitDate column is recognized as a date and Discharge_cfs / Turbidity_NTU as numbers, not text — misdetected types are a common, easy-to-miss import error.
- Click Load to bring the data into a new worksheet.
- In Google Sheets: File > Import > Upload, choose the CSV, and select "Insert new sheet."
- Rename the sheet Raw Data.

> **Practice on your own:** Open the CSV in a plain text editor (not Excel) first and look at the raw commas and line breaks. Seeing the unparsed structure makes it obvious what the import step is actually doing for you.

## Part 2: Import Data from a Web Source

Excel and Sheets can both pull a table directly off a webpage instead of a downloaded file.

- Open Wikipedia's [List of rivers of the United States by discharge](https://en.wikipedia.org/wiki/List_of_rivers_of_the_United_States_by_discharge) in your browser and note the URL and the fact that it has a plain, well-formed table — not every webpage does, and Excel/Sheets both do best with simple HTML tables rather than pages built with heavy JavaScript.
- In Excel: Data tab > Get Data > From Web (or just "From Web" in older versions). Paste the URL and click OK. The Navigator window will show every table Excel found on the page — preview a few until you find the river discharge table, then click Load.
- In Google Sheets: click an empty cell and type `=IMPORTHTML("https://en.wikipedia.org/wiki/List_of_rivers_of_the_United_States_by_discharge", "table", 1)` — the last argument is the table's position on the page, so if the first table isn't the right one, try 2, 3, and so on.
- Compare the two results: Excel's import is a one-time load you can right-click and Refresh later; the Sheets formula stays live and updates automatically whenever the source page changes.

> **Practice on your own:** Find a different Wikipedia page with a data table relevant to your own interests and import it using whichever method you didn't just use — Data > From Web in Excel, or IMPORTHTML in Sheets.

## Sample of the Monitoring Log

A preview of the CSV you imported in Part 1 — 96 rows total.

| Site | VisitDate | Discharge_cfs | Turbidity_NTU | Technician |
|---|---|---|---|---|
| Catawba Creek | 2025-01-15 | 26.6 | 5.9 | J. Alvarez |
| Stroubles Creek | 2025-01-15 | 28.9 | 11.7 | R. Okafor |
| Tinker Creek | 2025-01-15 | 62.3 | 9.4 | M. Pham |
| Toms Run | 2025-01-15 | 46.0 | 7.3 | J. Alvarez |
| ... | ... | ... | ... | ... |

## Part 3: Build a PivotTable

Use the Raw Data sheet from Part 1 for this section (the pre-built version, [nrv-monitoring-log-starter.xlsx](assets/nrv-monitoring-log-starter.xlsx), is also provided if you want to skip straight to pivoting).

- Click any cell inside your data, then Insert tab > PivotTable. Accept the default range and choose New Worksheet.
- Drag Site into the Rows area.
- Drag VisitDate into the Columns area. Excel will likely auto-group it into Years (and possibly Quarters) — this is Excel's automatic date/time grouping.
- Drag Discharge_cfs into the Values area. By default it will Sum — click the field, choose Value Field Settings, and change it to Average, since averaging a flow rate across a year is more physically meaningful than summing it.
- Rearrange the layout: drag Site out of Rows and into Columns, and drag the date field out of Columns and into Rows, so years run down the page instead of across it. Notice the summarized numbers don't change — only the layout does.
- Value Field Settings again: rename the field from "Average of Discharge_cfs" to "Avg Discharge (cfs)," and set its number format to show 1 decimal place.
- Right-click a date field in the PivotTable and choose Group. Try grouping by Quarters only (uncheck Years and Months) and see how the layout changes.

> **Practice on your own:** Add Turbidity_NTU to the Values area as a second summarized field, set it to Average as well, and identify which site has the highest average turbidity across the two years.

## Part 4: Slicers and PivotCharts

- Click anywhere in your PivotTable to activate the PivotTable Tools ribbon, then Analyze tab > Insert Slicer. Check Technician and click OK.
- Click a technician's name on the slicer to filter the whole PivotTable to just their visits. Hold Ctrl and click a second name to select multiple technicians at once.
- Clear the slicer filter (the small filter-clear icon in its corner) before continuing.
- With the PivotTable active, go to Analyze tab > PivotChart. Choose Clustered Column.
- The chart is dynamically linked to the PivotTable — change the PivotTable's layout (for example, swap which field is in Rows vs. Columns) and watch the chart update on its own.
- Click the slicer again with the chart visible: filtering the PivotTable filters the chart too.

> **Practice on your own:** Build a second PivotChart from the same PivotTable, but change the chart type to Line instead of Clustered Column. Which chart type actually communicates the seasonal pattern in discharge better — and why?

## Excel → Google Sheets Quick Reference

| Skill | Excel | Google Sheets |
|---|---|---|
| Import a CSV/text file | Data > Get Data > From File > From Text/CSV | File > Import > Upload |
| Import a web table | Data > Get Data > From Web | `=IMPORTHTML(url, "table", index)` in a cell |
| Create a PivotTable | Insert tab > PivotTable | Insert > Pivot table |
| Rearrange PivotTable fields | Drag fields between Rows/Columns/Values in the Field List | Same drag-and-drop in the Pivot table editor sidebar |
| Rename/format a value field | Click the field > Value Field Settings | Click the value in the editor > Summarize by / Format |
| Group dates in a PivotTable | Right-click a date field > Group | Right-click a date value > Create pivot date group |
| Add a Slicer | Analyze tab (PivotTable Tools) > Insert Slicer | Data > Add a slicer |
| Create a PivotChart | Analyze tab > PivotChart | Insert > Chart, with the pivot table as the data source |

## Skills Checklist

| Skill | What you did |
|---|---|
| Import a text/CSV file | Loaded an external CSV into a new worksheet |
| Import data from the web | Pulled a live table from a webpage into a worksheet |
| Understand common file formats | Compared CSV, text, and database sources and when each shows up in practice |
| Create a PivotTable | Summarized 96 rows of raw data into a compact table |
| Rearrange PivotTable fields | Moved fields between Rows, Columns, and Values |
| Value Field Settings | Renamed a summarized field and changed its number format |
| Group dates in a PivotTable | Collapsed monthly visit dates into years and quarters |
| Use a Slicer | Filtered a PivotTable interactively by technician |
| Create a PivotChart | Built a chart linked directly to a PivotTable |

## Resources

Full textbook chapters covered: [Ch. 21 – PivotTables and PivotCharts](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/pivottables-and-pivotcharts/) · [Ch. 22 – Importing Data into Excel](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/import-data-from-a-database/)

Files for this activity: [nrv-monitoring-log.csv](assets/nrv-monitoring-log.csv) (for Part 1's import) and [nrv-monitoring-log-starter.xlsx](assets/nrv-monitoring-log-starter.xlsx) (the same data pre-loaded as a formatted Excel Table, for Parts 3–4 if you want to jump ahead to PivotTables).

[← Back to all activities](index.html)
