# ScanDesk Desktop - beta test program

ScanDesk Desktop replaces PaperPort in a small medical office: scan, print-to-ScanDesk, file, find, clean up, annotate and send documents. Everything stays on your PC; nothing is uploaded. Source code is private; this page holds the installers.

**Current version: 0.12.8** (released 2026-11-09)

## Install (Windows 10/11, 64-bit)

1. **Trust the publisher (once per PC):** download [ScanDesk-Trust-Publisher.zip](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Trust-Publisher.zip), extract it, double-click `1-Trust-ScanDesk-Publisher.cmd` and approve the administrator prompt. This tells Windows that installers signed by "Mark Brown, MD" are trusted; without it SmartScreen shows a warning you can click through.
2. **Install:** download [ScanDesk-Setup.msi](https://github.com/msb2020-ux/scandesk-releases/releases/latest/download/ScanDesk-Setup.msi) and run it (one administrator prompt). Tick "Start ScanDesk Desktop now" at the end.
3. **Updates come by themselves:** ScanDesk checks this page at every start and offers new versions (Help > Check for updates does it on demand). Each package is verified against its checksum and signature before it installs.

## Sending feedback

Help > Copy logs for support writes the logs (file names and actions only, never document contents) to the diagnostics folder set in Options; send that folder, or describe what you saw and the version from Help > About.

## Release notes

## 0.12.8 - Folder changes are spelled out and logged (2026-11-09)
- Dragging a folder onto another folder in the tree now asks first ("Move the folder X and everything in it into Y?"),
  as PaperPort does. A slip of the mouse could silently move a whole year of documents.
- "Rename folder" now says which folder it renames and what it holds ("It holds 10 subfolders and 97 documents; they
  stay inside it under the new name. To add a folder inside it instead, use New folder"). "New folder" says where the
  new folder goes. The two buttons sit side by side on the toolbar; on 2026-11-06 a year folder was renamed to "10" by
  someone who meant to add a subfolder 10, and the year looked lost.
- Every folder create, rename, move, delete and import, and every move of documents, is now also written to the
  activity log (Help > Copy logs), with the old and new paths, so what happened can be read later without the database.