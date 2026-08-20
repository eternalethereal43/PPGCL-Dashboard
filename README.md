# Published data

The dashboard reads `manifest.json` on load and fetches the three workbooks
named in it from this folder.

| Key | Role | Sheet expectations |
| --- | --- | --- |
| `F` | Freight / RR | sheet `Assembled by RR`, header row 1 |
| `P` | Plant receipt / shortage | monthly sheets, header row 5 |
| `L` | Lab quality | monthly sheets, header row 4, PPGCL Lab Report block |

## Updating the figures each month

1. Replace the three `.xlsx` files in this folder, keeping the same filenames.
2. Change `updated` in `manifest.json` to the new as-at date. This is shown in
   the header bar so viewers know how current the figures are.
3. Commit. GitHub Pages rebuilds in a minute or two.

If a filename changes, edit the matching key in `manifest.json` rather than
renaming anything in `index.html`.

## If the manifest is missing

The dashboard falls back to manual upload boxes with no error. That is also
what happens when `index.html` is opened directly from disk, since browsers
block `fetch` on `file://` URLs.
