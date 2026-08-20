# Rake Reconciliation Dashboard

A single-file, browser-based dashboard that reconciles coal rake data across
three Excel workbooks — freight, plant weighbridge, and lab quality — joined on
RR number.

**Live:** https://YOUR-USERNAME.github.io/rake-dashboard/

## How it works

Open the link, drop in your three workbooks, and the dashboard renders
source-wise rake counts, quantity, shortage and GCV, with a date-range selector
and a styled Excel export.

**Your files never leave your computer.** They are read in the browser using the
FileReader API. There is no server, no database, no upload endpoint, and no
network request of any kind. Closing the tab discards everything.

## What's in this repository

| File | Purpose |
| --- | --- |
| `index.html` | The entire application — SheetJS and ExcelJS are inlined |
| `.gitignore` | Blocks workbooks, databases and credentials from being committed |

No build step. No dependencies. No install.

## Browser support

Chrome or Edge are recommended. The **Scan folder** button uses the File System
Access API, which is available in Chromium browsers over HTTPS. Firefox and
Safari can still use the three upload boxes normally.

## Local use

The file also works offline. Download `index.html` and double-click it — the
only feature that degrades is the folder scan, which browsers restrict on
`file://` URLs.

## A note on data

This repository contains application code only. No plant figures, RR numbers,
station data or lab results are stored here, and none should ever be committed.
The `.gitignore` is configured to prevent it.
