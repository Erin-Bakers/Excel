# Tab Groups – Excel add-in

A sidebar that organizes a workbook's tabs under master groups. Click a group to expand it, click a tab to jump to it.

## What it does
- **Groups**: add, rename (✎), recolor (◐) or delete (×) groups. Deleting a group never deletes tabs; they move to "Ungrouped".
- **Assign tabs**: use the ⋯ menu beside any tab to move it into a group. Tabs are tracked by internal ID, so renaming a tab doesn't break its group.
- **Tab colors**: tabs in a group get the group's color in Excel's tab bar.
- **Show only this group**: when on, opening a group hides every other tab in the tab bar. Turning it off unhides only the tabs the add-in hid; anything you hid yourself stays hidden.
- Groups are saved inside the workbook, so everyone who opens the file with the add-in sees the same structure. Save the workbook after changing groups.

## 1. Host the files
The add-in is a web page, so the files need an HTTPS address. Any of these work:
- **GitHub Pages** (free): create a repo, upload this folder as `tab-groups/`, turn on Pages.
- **Azure Static Web Apps / Azure Storage static site**, if IT prefers Microsoft hosting.

Then open `manifest.xml` and replace every `https://YOUR-HOST/tab-groups` with your real address (e.g. `https://yourname.github.io/tab-groups`).

## 2. Try it yourself
- **Excel on the web**: Home > Add-ins > More Add-ins > My Add-ins > Upload My Add-in > pick `manifest.xml`.
- **Excel for Windows**: put `manifest.xml` in a network shared folder, add that folder under File > Options > Trust Center > Trust Center Settings > Trusted Add-in Catalogs (check "Show in Menu"), restart Excel, then Home > Add-ins > More Add-ins > Shared Folder.

A **Tab Groups** button then appears on the Home tab.

## 3. Roll out to the team
A Microsoft 365 admin can deploy `manifest.xml` from the Microsoft 365 admin center (Settings > Integrated apps > Upload custom apps). It then shows up for assigned users automatically.

## Notes
- "Show only this group" really hides tabs in the file. In a co-authored workbook on SharePoint/OneDrive, that hides them for everyone editing at the same time, so leave it off in shared live files.
- Needs Excel 2019 / Microsoft 365 or newer (ExcelApi 1.7).
