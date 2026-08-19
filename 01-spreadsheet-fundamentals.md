---
layout: default
title: Spreadsheet Fundamentals
---

# Spreadsheet Fundamentals Activity
*Toms Run Monitoring Station — 2026 Monthly Water Quality Summary*

This activity walks through core spreadsheet skills in Excel and Google Sheets, using a monthly water-quality dataset. It follows Chapters 1–3 of [The Most EXCELlent OER Spreadsheets Textbook](https://minnstate.pressbooks.pub/spreadsheets2025/) (Lacher, 2025), an open-access resource you can revisit any time for more detail or extra practice.

*Note: the numbers below are illustrative, built to show a realistic seasonal pattern (higher flow in spring, lower flow and higher temperature in late summer) — they are not real measurements from an actual gauge.*

## The Dataset

| Month | Discharge (cfs) | Turbidity (NTU) | Water Temp (°F) |
|---|---|---|---|
| January | 45 | 8.2 | 38 |
| February | 52 | 9.5 | 40 |
| March | 78 | 22.4 | 48 |
| April | 95 | 31.0 | 55 |
| May | 68 | 18.6 | 62 |
| June | 40 | 11.2 | 70 |
| July | 22 | 6.8 | 75 |
| August | 18 | 5.5 | 76 |
| September | 25 | 7.9 | 68 |
| October | 35 | 10.1 | 58 |
| November | 50 | 14.3 | 47 |
| December | 60 | 16.7 | 40 |

## Part 1: Set Up the Workbook

Open a new workbook and save it as "Toms Run – [your name].xlsx" (or, in Google Sheets, just rename the file — it saves automatically).

- In cell A2, type `Month`. Press Tab and type `Discharge_cfs`, `Turbidity_NTU`, and `WaterTemp_F` across row 2.
- In A3, type `January` and press Enter. Reactivate A3, then drag the fill handle (the small square at the cell's bottom-right corner) down to A14 to auto-fill the rest of the months.
- Enter the Discharge, Turbidity, and Water Temp values from the table above into columns B–D, rows 3–14.

> **Practice on your own:** Enter the data for at least four months without looking back and forth constantly — get a feel for using Tab and Enter to move between cells.

- Practice editing a cell two ways: click a cell and edit its contents in the Formula Bar, or press F2 while the cell is active to edit in place.
- Delete a value, then press Ctrl+Z to undo the deletion.
- Widen column B so "Discharge_cfs" isn't cut off — drag the column border, or use Format > Column Width for an exact size.
- Insert a new column A and label it `Site`. Fill it with "Toms Run" for every row.
- Hide the Site column (Format > Hide & Unhide), then unhide it again.
- Insert a blank row above row 3, then delete it so your data stays contiguous.
- Drag a column to a new position, then undo the move so your original column order is restored.

## Part 2: Format the Worksheet

- Bold row 2 (the headers). Create a totals row in row 15 labeled "Avg / Total," and bold + italicize it.
- Add a bottom border under row 2, and a top-and-double-bottom border under row 15 — a standard way to mark totals.
- Apply number formatting: whole numbers with commas for Discharge, one decimal place for Turbidity, whole numbers for Water Temp. Match the precision to what the instrument can actually measure — don't show more decimal places than are meaningful.
- Center the column headers and turn on Wrap Text so long headers stack instead of getting cut off.
- Insert a row above row 1, merge A1:D1, and type a two-line title using Alt+Enter between lines — for example, "Toms Run Monitoring Station" then "2026 Monthly Water Quality Summary." Italicize it and increase the row height so both lines are visible.

> **Practice on your own:** Add a fill color to the header row and a font color that's readable against it — your choice.

## Part 3: Analyze the Data

- In row 15, use the AutoSum dropdown to calculate an average for each column (Discharge, Turbidity, Water Temp). Averaging makes more physical sense than summing for a flow rate like discharge.
- Select the Month column and the Discharge column (hold Ctrl to select both non-adjacent ranges), then insert a Clustered Column chart. Move and resize it next to your data.
- Look at the shape of the chart: where's the peak? Where's the low point? This is the shape of a hydrograph — a plot of streamflow over time.

## Part 4: Organize the Workbook

- Right-click the sheet tab, choose Move or Copy > Create a copy, and rename the new sheet "Sorted View."
- On the Sorted View sheet, sort the data by Discharge, largest to smallest (Data tab > Sort).
- Notice that once you sort by value, the Month column no longer reads in calendar order. For time-stamped data like this, that's a real risk: never sort your original, working copy of a time series — sort a duplicate, like you just did.
- Rename Sheet1 to "Monthly Data." Reorder the tabs so Monthly Data comes first. Insert a new blank sheet, then delete it — note that deleting a sheet cannot be undone once you close the file, so always double-check before confirming.

> **Practice on your own:** Rename one of your own sheet tabs to something of your choosing and reorder the tabs — without a reference in front of you.

## Excel → Google Sheets Quick Reference

| Skill | Excel | Google Sheets |
|---|---|---|
| Bold / Italic / Borders / Fill Color | Home tab > Font group | Toolbar icons, or Format > Text / Format > Borders |
| Number formatting (comma, decimals) | Home tab > Number group | Format > Number |
| Center, Wrap Text, Merge & Center | Home tab > Alignment group | Toolbar icons, or Format > Align / Wrap / Merge cells |
| AutoSum | Home or Formulas tab | Toolbar Σ icon, or type =SUM( / =AVERAGE( directly |
| Insert a chart | Insert tab > Column Chart | Insert > Chart, then set type in the Chart editor sidebar |
| Sort a range | Data tab > Sort | Data > Sort range (check "Data has header row") |
| Rename / move / delete a sheet tab | Right-click the sheet tab | Right-click the sheet tab — same options |
| Fill Handle / Auto Fill | Drag the small square at a cell's corner | Same — right-click-drag gives extra fill options |

## Skills Checklist

Use this to check your own progress or review before a quiz.

| Skill | What you did |
|---|---|
| Enter and edit data | Typed headers and values; edited a cell via the Formula Bar and F2 |
| Auto Fill | Filled the months of the year down a column |
| Delete data and Undo | Deleted a value and restored it with Ctrl+Z |
| Resize columns and rows | Widened a column and adjusted row height |
| Hide / unhide columns | Hid the Site column, then unhid it |
| Insert and delete rows/columns | Inserted a Site column and a spacer row, then removed the spacer |
| Move data | Dragged a column to a new position |
| Format cells | Bold, italic, borders, number formats (commas, decimal places) |
| Align data | Centered headers, wrapped text, merged & centered a title |
| Multi-line titles | Used Alt+Enter to start a second line inside a merged cell |
| AutoSum | Used Sum and Average from the AutoSum menu |
| Insert a chart | Built a column chart of monthly discharge |
| Cut, copy, paste | Duplicated a worksheet |
| Sort data | Sorted rows by discharge, largest to smallest |
| Manage worksheet tabs | Renamed, reordered, inserted, and deleted sheet tabs |

## Resources

Full textbook chapters covered: [Ch. 1 – An Overview of Excel](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/making-decisions-with-excel-2/) · [Ch. 2 – Entering, Editing, and Managing Data](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/making-decisions-with-excel/) · [Ch. 3 – Formatting and Data Analysis](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/formatting-and-data-analysis/)

Starter and completed example workbooks: [toms-run-starter.xlsx](assets/toms-run-starter.xlsx) · [toms-run-answer-key.xlsx](assets/toms-run-answer-key.xlsx) — use the completed version to check your own work, not as a shortcut to skip building it yourself.

[← Back to all activities](index.html)
