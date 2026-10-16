---
name: restaurant-list
description: "Add or update restaurants in the household Restaurant List Google Sheet from rating-site links (OpenRice, Tabelog, Google, etc.) or links with add-to-list comments. Ask for tab, tried status (dropdown), and confirmation before writing. Supports batches. Monthly backup. Not for bulk non-link imports or changing sheet structure."
---

# Restaurant List Skill

When the user shares one or more restaurant-rating-site links (OpenRice, Tabelog, Google, etc.) or a link plus a comment such as “add to the restaurant list” / “add to my favorite restaurant”:

1. Extract restaurant name, address, phone, and URL from each link (best-guess if incomplete).
2. Best-guess the tab (Office / Home / Others HK) from the address/area. Show the suggestion. Allow the user to correct it. Do not write yet.
3. Best-guess price range (below 100 / 100-200 / 200+) and walking distance to Lee Garden One (Office) if relevant. Leave blank if unsure. Include in the preview.
4. For each item, ask the user to set “Have I Tried” (yes / like to / not again). The sheet column is a dropdown of these three values.
5. If a restaurant already exists in the sheet, show the existing row and ask whether to update it or skip.
6. Show a clear preview of the full proposed row(s) (batch or single). Wait for an explicit “add” / “confirm” / “yes” (or equivalent) before writing.
7. Update the live Google Sheet “Restaurant List” in folder “04. Restaurant list” (ID 1AWG4fkfJhvixtM2VhISBR3XtabTKB6St). Append or update the matching row. Never delete the live sheet.
8. On the first run of each calendar month, copy the current sheet into a `backups` subfolder inside “04. Restaurant list” as a dated copy (e.g. Restaurant List YYYY-MM).

Never auto-write without confirmation. Never invent data beyond a labelled best-guess. Never change the existing column structure.
