# Confirmation Desk updates

The Confirmation Desk app on Fraser's Mac checks `manifest.json` here when it opens (and every 6 hours).
When `version` is newer than what's installed, it downloads `file`, checks it against `sha256`,
and offers "Restart to update".

- `version` – the new version number (must go up each time)
- `shell` – the oldest app install that can run this page. If it's newer than the installed app,
  the app says a fresh install is needed instead of updating itself.
- `file` – the page to download, relative to this folder
- `sha256` – SHA-256 of that file

To publish an update: upload the new `ui/ui-X.Y.Z.html`, then update `manifest.json`.
The page never contains client jobs – those stay on the Mac.
