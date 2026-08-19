---
layout: default
title: Formulas, Statistical Functions & Sorting
---

# Formulas, Statistical Functions & Sorting
*Watershed Site Comparison — New River Valley Monitoring Network*

This activity covers formulas, statistical functions, and sorting in Excel and Google Sheets, using a multi-site streamflow comparison instead of a generic example. It follows Chapters 5, 6, and 18 of [The Most EXCELlent OER Spreadsheets Textbook](https://minnstate.pressbooks.pub/spreadsheets2025/) (Lacher, 2025), an open-access resource you can revisit any time for more detail or extra practice. (Chapter 18 here covers sorting and custom lists; filtering is addressed separately in Chapter 19.)

*Note: all discharge and turbidity values below are illustrative — built to show realistic seasonal patterns across sites, not pulled from real gauge records.*

## Dataset A: Watershed Site Summary

Six sites in the New River Valley network, comparing January (high-flow) and July (low-flow) discharge.

| Site | Jan Discharge (cfs) | Jul Discharge (cfs) |
|---|---|---|
| Toms Run | 45 | 22 |
| Stroubles Creek | 30 | 15 |
| Tinker Creek | 60 | 28 |
| Catawba Creek | 25 | 12 |
| Poverty Creek | 18 | 8 |
| Craig Creek | 52 | 24 |

## Part 1: Formulas (Chapter 5)

Set up two new columns to the right of the data above: D = "Discharge_cms" and E = "Pct_Change_Jan_to_Jul." (Column A is Site, B is Jan Discharge, C is Jul Discharge.)

- **Basic formula:** in D2 (Toms Run's row), type `=B2*0.0283168` and press Enter. This converts cubic feet per second to cubic meters per second using a constant that never changes — a good use case for a typed-in number instead of a cell reference.
- **Relative referencing:** click D2, copy it, then paste into D3:D7. Double-click any pasted cell to confirm the row number in the formula updated automatically to match its own row.
- **Complex formula with order of operations:** in E2, build `=(C2−B2)/B2` — type `=`, type `(`, click the Jul Discharge cell (C2), type `−`, click the Jan Discharge cell (B2), type `)`, type `/`, click B2 again, then press Enter. Format the result as a percentage.
- Copy the E2 formula down to E3:E7 using the fill handle.

> **Practice on your own:** Before copying the formula down, predict whether the parentheses are actually necessary here — what would the result be without them? Then remove the parentheses on a spare cell and check your prediction.

- Every result in column E should be negative — confirm that makes sense given what January and July represent for streamflow in this region, and be able to explain why in one sentence.

## Part 2: Statistical Functions (Chapter 6)

Continue with Dataset A. Add a totals row below the six sites (row 8) and a percent-of-total column (F).

- In B8, use the AutoSum dropdown to insert `=SUM(B2:B7)` — total January discharge across the network.
- In C8, use AutoSum again but choose Average instead of Sum.
- In a nearby cell, use `=COUNT(B2:B7)` to confirm the network has six reporting sites.
- In two more cells, use `=MIN(B2:B7)` and `=MAX(B2:B7)` to find the lowest- and highest-flow sites in January.
- **Absolute references:** in F2, type `=B2/$B$8` to calculate each site's percent of total January discharge. The dollar signs lock the reference to B8 so it doesn't shift when you copy the formula down — without them, F3 would try to divide by B9, which is empty.
- Copy F2 down to F3:F7 and confirm the percentages add up to 100%.
- **Copy/paste formulas without formatting:** copy any of your finished formula cells, right-click a blank cell, and choose Paste Special > Formulas. Notice the value and formula come through but the cell keeps its own formatting instead of inheriting borders or fill color from the source.

> **Practice on your own:** Add a MAX and MIN for the July column as well, and identify which site had the biggest percentage drop in flow between January and July — use your Part 1 results, don't recalculate by hand.

## Dataset B: 2026 Monitoring Visit Log

A longer, record-style table — four sites, visited in January, April, and July.

| Site | Month | Discharge (cfs) | Turbidity (NTU) |
|---|---|---|---|
| Toms Run | January | 45 | 8.2 |
| Toms Run | April | 95 | 31.0 |
| Toms Run | July | 22 | 6.8 |
| Stroubles Creek | January | 30 | 12.5 |
| Stroubles Creek | April | 68 | 40.2 |
| Stroubles Creek | July | 15 | 9.1 |
| Tinker Creek | January | 60 | 9.0 |
| Tinker Creek | April | 120 | 28.4 |
| Tinker Creek | July | 28 | 7.5 |
| Catawba Creek | January | 25 | 6.5 |
| Catawba Creek | April | 55 | 20.1 |
| Catawba Creek | July | 12 | 5.0 |

## Part 3: Sorting (Chapter 18)

- Enter Dataset B into a new worksheet, with headers in row 1.
- **Single-column sort:** click the dropdown arrow on the Discharge column header and sort largest to smallest.
- **Multi-level sort:** open Data tab > Sort. Set the first level to sort by Site (A to Z). Click Add Level and set the second level to sort by Month.
- Run that sort now and look at the Month order within each site — alphabetically, April comes before January, which comes before July. That's not calendar order, and for monitoring data, calendar order is usually what you actually want.
- **Fix it with a custom list:** in the second sort level, open the Order dropdown and choose Custom List. Create a new list with January, April, July typed in that order, click OK, then OK again to re-run the sort.
- Confirm each site's three visits now appear in calendar order instead of alphabetical order.

> **Practice on your own:** Custom lists apply across your whole Excel installation once created, not just one workbook. Open the Custom Lists dialog box directly (File > Options > Advanced > Edit Custom Lists) and see what lists already exist — the days of the week and months of the year are already built in, which is why Auto Fill already knew how to fill month names in earlier activities.

## Quick Reference: Order of Operations

| Symbol | Operation | Order |
|---|---|---|
| ^ | Exponent | 1st |
| * or / | Multiply or divide | 2nd (left to right) |
| + or − | Add or subtract | 3rd (left to right) |
| ( ) | Parentheses — overrides the order above | Innermost first |

## Skills Checklist

| Skill | What you did |
|---|---|
| Basic formulas | Wrote a formula with a cell reference and a constant |
| Relative referencing | Copied a formula down a column and watched the row number adjust automatically |
| Complex formulas / order of operations | Used parentheses to force subtraction before division in a percent-change formula |
| SUM, COUNT, AVERAGE, MIN, MAX | Summarized a column of discharge values with statistical functions |
| AutoSum | Inserted a function quickly from the AutoSum dropdown |
| Absolute references | Locked a cell reference with $ signs to calculate percent of total |
| Copy/paste formulas without formatting | Used Paste Special > Formulas to copy a calculation without carrying over borders or fill color |
| Single-column sort | Sorted a table by one column using the column header dropdown |
| Multi-level sort | Sorted by Site, then by Month, using the Sort dialog box |
| Custom list sort | Built a custom list so months sort in calendar order instead of alphabetical order |

## Resources

Full textbook chapters covered: [Ch. 5 – Formulas](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/formulas/) · [Ch. 6 – Statistical Functions](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/statistical-functions/) · [Ch. 18 – Sorting and Filtering Data](https://minnstate.pressbooks.pub/spreadsheets2025/chapter/sorting-and-filtering-data/)

[← Back to all activities](index.html)
