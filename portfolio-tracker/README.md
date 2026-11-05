# Portfolio Tracker

One HTML file (`portfolio-tracker.html`) with three pages: KPI overview, Projects board and Project.
The project management data (projects, actions, risks, comments, savings) lives in a local Excel file.

## Setup

1. Put `portfolio-tracker.html` in a folder, for example a OneDrive or SharePoint-synced folder that the team shares.
2. Open it by double-clicking. Use **Edge or Chrome**. Firefox and Safari can only read a file, not save to it.
3. Click **Create Excel data file** and save it as `pm-data.xlsx` next to the tool. This writes the current data (sample data the first time) into the workbook.
   If a data file already exists, click **Open Excel data file** instead.
4. Allow the browser to edit the file when it asks. From then on, every change in the tool is saved to the workbook automatically.
   Next time you open the tool, it offers **Reconnect** to the same file.

The tool needs internet access once per load to fetch the Excel library from cdnjs.cloudflare.com.

## The workbook

| Sheet | One row per |
|---|---|
| Projects | project (stage, status, focus flag, PM checklist, finalization) |
| Actions | action, linked by Project ID |
| Risks | risk or issue, linked by Project ID |
| Comments | comment, linked by Item ID (Action ID or Risk ID) |
| Savings | project, benefit type and year (also filled by the Sievo import) |
| Read me | allowed values and editing rules |

You can edit the workbook in Excel, for example to add many actions at once. Leave the Action ID or Risk ID empty for new rows; the tool fills them in.

- Close the tool before editing in Excel, and close Excel before using the tool again. Excel locks the file while it is open, and the tool then shows "The file is locked".
- Keep the sheet names and column headings. Formatting, formulas and extra sheets are not kept when the tool saves.

## Several people on one file

- The tool checks the file every 20 seconds and loads changes other people saved.
- If someone else saved while you had an unsaved change, the tool stops and asks: **Load their version** or **Keep mine and overwrite**.
- OneDrive can still create a "conflict copy" if two people save at the same second. Check the folder now and then.

## Sievo import

**Import Sievo export** reads a CSV file and replaces the projects and savings, while keeping actions, risks and checklists for projects with the same ID.
The column mapping is a first guess until we have a real export.
